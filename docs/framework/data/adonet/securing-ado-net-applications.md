---
title: ADO.NET 응용 프로그램 보안
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: e5b99621989e9f14c6c734a497f210780f3c7e57
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526971"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="eaeed-102">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="eaeed-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="eaeed-103">보안 ADO.NET 응용 프로그램을 작성하려면 사용자 입력의 유효성을 확인하지 않는 것과 같은 일반적인 코딩 문제를 피하는 것 외에도 여러 부분을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="eaeed-104">데이터에 액세스하는 응용 프로그램에는 공격자가 중요한 데이터를 검색, 조작 또는 파괴하는 데 악용할 수 있는 여러 잠재적인 오류 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="eaeed-105">따라서 응용 프로그램 디자인 단계의 위협 모델링 과정에서부터 최종 배포와 진행 중인 유지 관리에 이르기까지 보안의 모든 측면을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="eaeed-106">.NET Framework에서는 데이터베이스 응용 프로그램을 보호하고 관리할 수 있는 여러 유용한 클래스, 서비스 및 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="eaeed-107">CLR(공용 언어 런타임)은 관리 코드의 권한을 더 제한하는 CAS(코드 액세스 보안)를 사용하여 실행될 코드에 형식 안전 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="eaeed-108">다음 보안 데이터 액세스 코딩 연습에서는 잠재적인 공격자에 의해 발생할 수 있는 손상을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="eaeed-109">보안 코드를 작성하면 데이터베이스와 같은 관리되지 않는 리소스 작업을 할 때 자초한 보안 허점을 막지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="eaeed-110">SQL Server와 같은 대부분의 서버 데이터베이스는 제대로 구현되는 경우 보안을 강화하는 자체 보안 시스템을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="eaeed-111">그러나 제대로 구성되지 않은 경우 강력한 보안 시스템으로 구성된 데이터 소스라 할지라도 공격에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eaeed-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="eaeed-112">In This Section</span></span>  
 [<span data-ttu-id="eaeed-113">보안 개요</span><span class="sxs-lookup"><span data-stu-id="eaeed-113">Security Overview</span></span>](../../../../docs/framework/data/adonet/security-overview.md)  
 <span data-ttu-id="eaeed-114">보안 ADO.NET 응용 프로그램 디자인에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="eaeed-115">보안 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="eaeed-115">Secure Data Access</span></span>](../../../../docs/framework/data/adonet/secure-data-access.md)  
 <span data-ttu-id="eaeed-116">안전한 데이터 소스의 데이터로 작업하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="eaeed-117">안전한 클라이언트 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="eaeed-117">Secure Client Applications</span></span>](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 <span data-ttu-id="eaeed-118">클라이언트 응용 프로그램 보안을 위한 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="eaeed-119">코드 액세스 보안 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eaeed-119">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)  
 <span data-ttu-id="eaeed-120">CAS를 사용하여 ADO.NET 코드를 보호하는 방법 및</span><span class="sxs-lookup"><span data-stu-id="eaeed-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="eaeed-121">부분 신뢰를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="eaeed-122">개인 정보 및 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="eaeed-122">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 <span data-ttu-id="eaeed-123">ADO.NET 응용 프로그램의 암호화 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eaeed-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="eaeed-124">Related Sections</span></span>  
 [<span data-ttu-id="eaeed-125">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="eaeed-125">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="eaeed-126">개발자 관점에서 SQL Server 보안 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="eaeed-127">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="eaeed-127">Security Considerations</span></span>](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 <span data-ttu-id="eaeed-128">Entity Framework 응용 프로그램의 보안에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="eaeed-129">보안</span><span class="sxs-lookup"><span data-stu-id="eaeed-129">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="eaeed-130">.NET에서 보안의 여러 가지 측면에 대해 설명하는 항목의 링크가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 [<span data-ttu-id="eaeed-131">보안 도구</span><span class="sxs-lookup"><span data-stu-id="eaeed-131">Security Tools</span></span>](https://msdn.microsoft.com/library/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 <span data-ttu-id="eaeed-132">보안 정책을 보호하고 관리하는 .NET Framework 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 [<span data-ttu-id="eaeed-133">보안 응용 프로그램을 만들기 위한 리소스</span><span class="sxs-lookup"><span data-stu-id="eaeed-133">Resources for Creating Secure Applications</span></span>](https://msdn.microsoft.com/library/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 <span data-ttu-id="eaeed-134">보안 응용 프로그램 만들기에 대한 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="eaeed-135">보안 관련 참조 목록</span><span class="sxs-lookup"><span data-stu-id="eaeed-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="eaeed-136">온라인 및 인쇄 작업에서 사용 가능한 외부 리소스의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeed-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaeed-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaeed-137">See Also</span></span>  
 [<span data-ttu-id="eaeed-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eaeed-138">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="eaeed-139">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="eaeed-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
