---
title: 형식 공급자 보안
description: '형식 공급자의 신뢰 설정을 변경 하는 방법을 포함 하 여 F # 형식 공급자 보안에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 26f95ad3950b37a668c497f293b9941ed13a18c7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861909"
---
# <a name="type-provider-security"></a><span data-ttu-id="a6f33-103">형식 공급자 보안</span><span class="sxs-lookup"><span data-stu-id="a6f33-103">Type Provider Security</span></span>

<span data-ttu-id="a6f33-104">형식 공급자는 어셈블리 (Dll) F # 프로젝트 또는 스크립트에서 참조 된 외부 데이터 원본에 연결 하 여 F # 형식 환경에이 형식 정보를 노출 하는 코드를 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-104">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="a6f33-105">일반적으로 참조 된 어셈블리의 코드를 컴파일 및 다음 코드를 실행 (또는 스크립트의 경우 코드는 F # Interactive로 보내기) 하는 경우에 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-105">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="a6f33-106">그러나 편집기에서 코드를 단순히 찾아볼 때 형식 공급자 어셈블리를 Visual Studio 내에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-106">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="a6f33-107">이 형식 공급자를 실행 하 고 IntelliSense 완성, 빠른 정보 도구 설명 등의 편집기를에 추가 정보를 추가 해야 하기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-107">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="a6f33-108">결과적으로, 추가 보안 고려 사항이 형식에 대 한 공급자 어셈블리를 Visual Studio 프로세스 내에서 자동으로 실행 되므로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-108">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>

## <a name="security-warning-dialog"></a><span data-ttu-id="a6f33-109">보안 경고 대화 상자</span><span class="sxs-lookup"><span data-stu-id="a6f33-109">Security Warning Dialog</span></span>

<span data-ttu-id="a6f33-110">처음으로 특정 형식의 공급자 어셈블리를 사용 하는 경우 Visual Studio 형식 공급자 실행을 경고 하는 보안 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-110">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="a6f33-111">Visual Studio 형식 공급자를 로드 하기 전에이 특정 공급자를 신뢰 하는 경우를 결정할 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-111">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="a6f33-112">형식 공급자의 소스를 신뢰 하는 경우 선택한 "이 형식 공급자를 신뢰 합니다."</span><span class="sxs-lookup"><span data-stu-id="a6f33-112">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="a6f33-113">형식 공급자의 소스를 신뢰 하지 않는다면 선택한 "신뢰할이 형식 공급자입니다."</span><span class="sxs-lookup"><span data-stu-id="a6f33-113">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="a6f33-114">공급자를 신뢰를 사용 하면 Visual Studio 내에서 실행 하 고 IntelliSense를 제공할 기능을 구축할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-114">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="a6f33-115">하지만 악성 자체 형식 공급자 인 경우 해당 코드 실행을 손상 시킬 수 컴퓨터.</span><span class="sxs-lookup"><span data-stu-id="a6f33-115">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="a6f33-116">프로젝트에 코드가 신뢰할 수 없다는 대화 상자에서 선택한 형식 공급자를 참조 하는 경우 다음 컴파일 타임에 컴파일러 오류를 보고 합니다 형식 공급자를 신뢰할 수 있는 아님을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-116">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="a6f33-117">신뢰할 수 없는 형식 공급자에 종속 된 모든 형식은 빨간색 물결선으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-117">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="a6f33-118">편집기에서 코드를 찾아보려면 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-118">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="a6f33-119">Visual Studio에서 직접 신뢰 설정을 변경 하려는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-119">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>

### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="a6f33-120">형식 공급자에 대 한 트러스트 설정을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="a6f33-120">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="a6f33-121">에 `Tools` 메뉴에서 `Options`, 확장을 `F# Tools` 노드.</span><span class="sxs-lookup"><span data-stu-id="a6f33-121">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>

2. <span data-ttu-id="a6f33-122">선택 `Type Providers`, 형식 공급자의 목록에서 신뢰 하는 형식 공급자에 대 한 확인란을 선택 하 고 신뢰할 수 없는 것에 대 한 확인란의 선택을 취소 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f33-122">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f33-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="a6f33-123">See also</span></span>

- [<span data-ttu-id="a6f33-124">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="a6f33-124">Type Providers</span></span>](index.md)
