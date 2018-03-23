---
title: -removeintchecks
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25a14ffaca6e61c6e3306f8ff58de441e2ba2ade
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-removeintchecks"></a><span data-ttu-id="1c493-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="1c493-102">-removeintchecks</span></span>
<span data-ttu-id="1c493-103">오버플로 오류 설정 하거나 해제 하는 정수 연산에 대 한 검사를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c493-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c493-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1c493-105">인수</span><span class="sxs-lookup"><span data-stu-id="1c493-105">Arguments</span></span>  
  
|<span data-ttu-id="1c493-106">용어</span><span class="sxs-lookup"><span data-stu-id="1c493-106">Term</span></span>|<span data-ttu-id="1c493-107">정의</span><span class="sxs-lookup"><span data-stu-id="1c493-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="1c493-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1c493-108">`+` &#124; `-`</span></span>|<span data-ttu-id="1c493-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-109">Optional.</span></span> <span data-ttu-id="1c493-110">`-removeintchecks-` 옵션을 사용 하면 오버플로 오류에 대 한 모든 정수 연산 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="1c493-111">기본값은 `-removeintchecks-`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="1c493-112">지정 `-removeintchecks` 또는 `-removeintchecks+` 오류 검사를 차단 하 고 정수 계산을 더욱 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="1c493-113">오류를 검사 하지 않는 반면 및 잘못 된 결과 데이터 형식 용량 오버플로 하는 경우 오류를 일으키지 않고 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="1c493-114">-Removeintchecks Visual Studio 통합된 개발 환경에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1c493-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1c493-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1c493-116">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1c493-117">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1c493-118">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="1c493-119">4.  값을 수정 된 **정수 오버플로 검사 해제** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1c493-120">예제</span><span class="sxs-lookup"><span data-stu-id="1c493-120">Example</span></span>  
 <span data-ttu-id="1c493-121">다음 코드에서는 `Test.vb` 정수 오버플로 오류 검사를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c493-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c493-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c493-122">See Also</span></span>  
 [<span data-ttu-id="1c493-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1c493-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1c493-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="1c493-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
