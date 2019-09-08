---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 017fe2177cf824d461b4c51ea805f75b6ddbe064
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779997"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="c2ee3-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="c2ee3-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="c2ee3-103">WCF Data Services (이전의 "ADO.NET Data Services")는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] [representational 상태의 의미 체계를 사용 하 여 웹 또는 인트라넷을 통해 데이터를 노출 하 고 사용 하기 위해을 사용 하는 서비스를 만들 수 있는 .NET Framework의 구성 요소입니다. 전송 (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="c2ee3-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="c2ee3-104">OData는 URI로 주소를 지정할 수 있는 리소스로 데이터를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="c2ee3-105">데이터는 표준 HTTP 동사인 GET, PUT, POST 및 DELETE를 사용하여 액세스되고 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="c2ee3-106">OData는 [엔터티 데이터 모델](../adonet/entity-data-model.md) 의 엔터티-관계 규칙을 사용 하 여 리소스를 연결로 관련 된 엔터티 집합으로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="c2ee3-107">WCF Data Services는 OData 프로토콜을 사용 하 여 리소스의 주소를 지정 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="c2ee3-108">이러한 방식으로 OData를 지 원하는 모든 클라이언트에서 이러한 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="c2ee3-109">OData를 사용 하면 잘 알려진 전송 형식을 사용 하 여 리소스를 요청 하 고 리소스에 데이터를 쓸 수 있습니다. 데이터를 XML로 교환 및 업데이트 하기 위한 표준 집합인 Atom, AJAX 응용 프로그램에서 광범위 하 게 사용 되는 텍스트 기반 데이터 교환 형식인 JSON (JavaScript Object Notation)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="c2ee3-110">WCF Data Services는 다양 한 원본에서 가져온 데이터를 OData 피드로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="c2ee3-111">Visual Studio 도구를 사용 하면 ADO.NET Entity Framework 데이터 모델을 사용 하 여 OData 기반 서비스를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="c2ee3-112">CLR (공용 언어 런타임) 클래스와 런타임에 바인딩된 데이터 나 형식화 되지 않은 데이터를 기반으로 하 여 OData 피드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="c2ee3-113">또한 WCF Data Services에는 클라이언트 라이브러리 집합, 일반 .NET Framework 클라이언트 응용 프로그램 및 Silverlight 기반 응용 프로그램용 기타 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="c2ee3-114">이러한 클라이언트 라이브러리는 .NET Framework 및 Silverlight와 같은 환경에서 OData 피드에 액세스할 때 개체 기반 프로그래밍 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="c2ee3-115">시작 지점</span><span class="sxs-lookup"><span data-stu-id="c2ee3-115">Where Should I Start?</span></span>

<span data-ttu-id="c2ee3-116">관심 사항에 따라 다음 항목 중 하나를 사용 하 여 WCF Data Services 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="c2ee3-117">바로 시작...</span><span class="sxs-lookup"><span data-stu-id="c2ee3-117">I want to jump right in...</span></span>

- [<span data-ttu-id="c2ee3-118">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="c2ee3-119">시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

- [<span data-ttu-id="c2ee3-120">Silverlight 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="c2ee3-121">Windows Phone 개발을 위한 Silverlight 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="c2ee3-122">코드를 표시 하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-122">Just show me some code...</span></span>

- [<span data-ttu-id="c2ee3-123">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-123">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="c2ee3-124">방법: 데이터 서비스 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="c2ee3-124">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="c2ee3-125">방법: Windows Presentation Foundation 요소에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="c2ee3-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="c2ee3-126">OData에 대 한 자세한 내용을 확인 하려면 ...</span><span class="sxs-lookup"><span data-stu-id="c2ee3-126">I want to know more about OData...</span></span>

- [<span data-ttu-id="c2ee3-127">백서 OData 소개</span><span class="sxs-lookup"><span data-stu-id="c2ee3-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="c2ee3-128">Open Data Protocol 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="c2ee3-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

- [<span data-ttu-id="c2ee3-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="c2ee3-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

- [<span data-ttu-id="c2ee3-130">OData: 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="c2ee3-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="c2ee3-131">일부 비디오를 시청 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-131">I want to watch some videos...</span></span>

- [<span data-ttu-id="c2ee3-132">WCF Data Services 초보자 가이드</span><span class="sxs-lookup"><span data-stu-id="c2ee3-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

- [<span data-ttu-id="c2ee3-133">WCF Data Services 개발자 비디오</span><span class="sxs-lookup"><span data-stu-id="c2ee3-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

- [<span data-ttu-id="c2ee3-134">OData: 개발자 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="c2ee3-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="c2ee3-135">종단 간 샘플을 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-135">I want to see end-to-end samples...</span></span>

- [<span data-ttu-id="c2ee3-136">MSDN 샘플 갤러리의 WCF Data Services 설명서 샘플</span><span class="sxs-lookup"><span data-stu-id="c2ee3-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

- [<span data-ttu-id="c2ee3-137">MSDN 샘플 갤러리의 기타 WCF Data Services 샘플</span><span class="sxs-lookup"><span data-stu-id="c2ee3-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

- [<span data-ttu-id="c2ee3-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="c2ee3-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="c2ee3-139">Visual Studio와의 통합 방식</span><span class="sxs-lookup"><span data-stu-id="c2ee3-139">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="c2ee3-140">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="c2ee3-140">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="c2ee3-141">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c2ee3-141">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="c2ee3-142">Entity Framework 공급자</span><span class="sxs-lookup"><span data-stu-id="c2ee3-142">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="c2ee3-143">수행 가능 작업</span><span class="sxs-lookup"><span data-stu-id="c2ee3-143">What can I do with it?</span></span>

- [<span data-ttu-id="c2ee3-144">개요</span><span class="sxs-lookup"><span data-stu-id="c2ee3-144">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="c2ee3-145">백서 OData 소개</span><span class="sxs-lookup"><span data-stu-id="c2ee3-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="c2ee3-146">애플리케이션 시나리오</span><span class="sxs-lookup"><span data-stu-id="c2ee3-146">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="c2ee3-147">Silverlight를 사용 하려는 경우 ...</span><span class="sxs-lookup"><span data-stu-id="c2ee3-147">I want to use Silverlight...</span></span>

- [<span data-ttu-id="c2ee3-148">Silverlight 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="c2ee3-149">WCF Data Services(Silverlight)</span><span class="sxs-lookup"><span data-stu-id="c2ee3-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

- [<span data-ttu-id="c2ee3-150">Silverlight 시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="c2ee3-151">LINQ를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-151">I want to use LINQ...</span></span>

- [<span data-ttu-id="c2ee3-152">데이터 서비스 쿼리</span><span class="sxs-lookup"><span data-stu-id="c2ee3-152">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="c2ee3-153">LINQ 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c2ee3-153">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="c2ee3-154">방법: 데이터 서비스 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="c2ee3-154">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="c2ee3-155">추가 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-155">I still need some more information...</span></span>

- [<span data-ttu-id="c2ee3-156">WCF Data Services 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="c2ee3-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

- [<span data-ttu-id="c2ee3-157">리소스</span><span class="sxs-lookup"><span data-stu-id="c2ee3-157">Resources</span></span>](wcf-data-services-resources.md)

- [<span data-ttu-id="c2ee3-158">WCF Data Services 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c2ee3-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

- [<span data-ttu-id="c2ee3-159">Open Data Protocol 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="c2ee3-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="c2ee3-160">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c2ee3-160">In This Section</span></span>

[<span data-ttu-id="c2ee3-161">개요</span><span class="sxs-lookup"><span data-stu-id="c2ee3-161">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="c2ee3-162">WCF Data Services에서 사용 가능한 기능에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="c2ee3-163">[WCF Data Services 5.0의 새로운 기능](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="c2ee3-163">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="c2ee3-164">WCF Data Services의 새로운 기능 및 새로운 OData 기능에 대 한 지원을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="c2ee3-165">시작</span><span class="sxs-lookup"><span data-stu-id="c2ee3-165">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="c2ee3-166">WCF Data Services를 사용 하 여 OData 피드를 노출 하 고 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="c2ee3-167">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="c2ee3-167">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="c2ee3-168">OData 피드를 노출 하는 데이터 서비스를 만들고 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="c2ee3-169">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c2ee3-169">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="c2ee3-170">클라이언트 라이브러리를 사용 하 여 .NET Framework 클라이언트 응용 프로그램에서 OData 피드를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ee3-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2ee3-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2ee3-171">See also</span></span>

- [<span data-ttu-id="c2ee3-172">REST(Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="c2ee3-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
