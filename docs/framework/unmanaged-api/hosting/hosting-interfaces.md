---
title: 호스팅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e330e0d06077d1eef63cf44f31bbcbf7c3431b59
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303311"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="1c6ac-102">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c6ac-102">Hosting Interfaces</span></span>
<span data-ttu-id="1c6ac-103">이 섹션에서는 관리 되지 않는 인터페이스를 설명 합니다. 호스트 응용 프로그램에는 CLR (공용 언어 런타임) 통합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="1c6ac-104">.NET Framework 버전 2.0 호스팅 인터페이스에는.NET Framework 버전 1.0 및 1.1 인터페이스 보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="1c6ac-105">인터페이스의 두 집합 간의 중요 한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="1c6ac-106">인터페이스를 혼합 해 예기치 않은 동작이 발생할 수 있으며 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="1c6ac-107">.NET Framework 버전 3.0 및 3.5는.NET Framework 버전 2.0 호스팅 인터페이스를 사용 하 여 및 호스팅 기능을 도입 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="1c6ac-108">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 호스팅 인터페이스는.NET Framework 2.0 인터페이스를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="1c6ac-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1c6ac-109">In This Section</span></span>  
 [<span data-ttu-id="1c6ac-110">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="1c6ac-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="1c6ac-111">.NET Framework 버전 1.0 및 1.1에에서 도입 된 호스팅 인터페이스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="1c6ac-112">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c6ac-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="1c6ac-113">.NET Framework 버전 2.0에에서 도입 된 호스팅 인터페이스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="1c6ac-114">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c6ac-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="1c6ac-115">에 도입 된 호스팅 인터페이스를 설명 합니다 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6ac-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1c6ac-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1c6ac-116">Related Sections</span></span>  
 [<span data-ttu-id="1c6ac-117">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="1c6ac-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="1c6ac-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="1c6ac-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="1c6ac-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="1c6ac-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="1c6ac-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="1c6ac-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="1c6ac-121">호스팅</span><span class="sxs-lookup"><span data-stu-id="1c6ac-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="1c6ac-122">[런타임 호스트](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1c6ac-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
