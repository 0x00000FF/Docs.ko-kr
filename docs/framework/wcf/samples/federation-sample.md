---
title: "Federation 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b66bf65ba6165902eb90191a262f2715424d8b7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="federation-sample"></a><span data-ttu-id="35d92-102">Federation 샘플</span><span class="sxs-lookup"><span data-stu-id="35d92-102">Federation Sample</span></span>
<span data-ttu-id="35d92-103">이 샘플에서는 연결된 보안을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="35d92-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="35d92-104">Sample Details</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="35d92-105">에서는 `wsFederationHttpBinding`을 통해 연결된 보안 아키텍처의 배포를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-105"> provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="35d92-106">`wsFederationHttpBinding`에서는 요청/회신 통신의 기본 전송 메커니즘으로 HTTP를 사용하고, 인코딩 통신 형식으로 텍스트/XML을 사용하는, 안전하고 안정적이며 상호 운용 가능한 바인딩을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="35d92-107">페더레이션에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], 참조 [페더레이션](../../../../docs/framework/wcf/feature-details/federation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-107"> Federation in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see [Federation](../../../../docs/framework/wcf/feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="35d92-108">이 시나리오는 네 부분으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-108">The scenario is made up of 4 pieces:</span></span>  
  
-   <span data-ttu-id="35d92-109">BookStore 서비스</span><span class="sxs-lookup"><span data-stu-id="35d92-109">BookStore service</span></span>  
  
-   <span data-ttu-id="35d92-110">BookStore STS</span><span class="sxs-lookup"><span data-stu-id="35d92-110">BookStore STS</span></span>  
  
-   <span data-ttu-id="35d92-111">HomeRealm STS</span><span class="sxs-lookup"><span data-stu-id="35d92-111">HomeRealm STS</span></span>  
  
-   <span data-ttu-id="35d92-112">BookStore 클라이언트</span><span class="sxs-lookup"><span data-stu-id="35d92-112">BookStore Client</span></span>  
  
 <span data-ttu-id="35d92-113">BookStore 서비스는 `BrowseBooks`와 `BuyBook`의 두 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="35d92-114">`BrowseBooks` 작업에 대해서는 익명 액세스를 허용하지만, `BuyBooks` 작업에 액세스하려면 인증 액세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="35d92-115">인증은 BookStore STS에서 발급한 토큰의 형태로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="35d92-116">BookStore 서비스의 구성 파일은 `wsFederationHttpBinding`을 사용하여 클라이언트를 BookStore STS로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="35d92-117">그러면 BookStore STS는 클라이언트에게 HomeRealm STS에서 발급한 토큰을 사용하여 인증하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="35d92-118">BookStore STS의 구성 파일도 `wsFederationHttpBinding`을 사용하여 클라이언트를 HomeRealm STS로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="35d92-119">`BuyBook` 작업에 액세스할 때의 이벤트 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1.  <span data-ttu-id="35d92-120">클라이언트는 Windows 자격 증명을 사용하여 HomeRealm STS에 대해 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2.  <span data-ttu-id="35d92-121">HomeRealm STS는 BookStore STS에 대한 인증에 사용할 수 있는 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3.  <span data-ttu-id="35d92-122">클라이언트는 HomeRealm STS에서 발급한 토큰을 사용하여 BookStore STS에 대해 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4.  <span data-ttu-id="35d92-123">BookStore STS가 BookStore 서비스에 대한 인증에 사용할 수 있는 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5.  <span data-ttu-id="35d92-124">클라이언트는 BookStore STS에서 발급한 토큰을 사용하여 BookStore 서비스에 대해 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6.  <span data-ttu-id="35d92-125">클라이언트가 `BuyBook` 작업에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="35d92-126">이 샘플의 설치 및 실행 방법에 대해서는 다음 지침을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="35d92-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35d92-127">에 대 한 쓰기 권한이 있어야 합니다.는 **wwwroot** 이 샘플을 실행 하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="35d92-128">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="35d92-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="35d92-129">SDK 명령 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-129">Open the SDK command window.</span></span> <span data-ttu-id="35d92-130">샘플 경로에서 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="35d92-131">그러면 샘플에 필요한 가상 디렉터리가 만들어지고 적절한 권한과 함께 필요한 인증서가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35d92-132">Setup.bat 배치 파일은 Windows SDK 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="35d92-133">MSSDK 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="35d92-134">이 환경 변수는 Windows SDK 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="35d92-135">설치에서 IIS 관리자 스크립트를 사용하므로 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 IIS 6.0 관리 호환성이 설치되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-135">On [!INCLUDE[wv](../../../../includes/wv-md.md)], you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="35d92-136">[!INCLUDE[wv](../../../../includes/wv-md.md)]에서 설치 스크립트를 실행하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-136">Running the set-up script on [!INCLUDE[wv](../../../../includes/wv-md.md)] requires administrator privileges.</span></span>  
  
2.  <span data-ttu-id="35d92-137">Visual Studio에서 FederationSample.sln을 열고 선택 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="35d92-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="35d92-138">그러면 일반 프로젝트 파일, Bookstore 서비스, Bookstore STS 및 HomeRealm STS를 빌드하고 IIS에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="35d92-139">또한 Bookstore 클라이언트 응용 프로그램도 빌드하며, BookStoreClient.exe 실행 파일을 FederationSample\BookStoreClient\bin\Debug 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3.  <span data-ttu-id="35d92-140">BookStoreClient.exe를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="35d92-141">BookStoreClient 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-141">The BookStoreClient window is displayed.</span></span>  
  
4.  <span data-ttu-id="35d92-142">클릭 하 여 서 점에서 판매 책을 찾아볼 수 **Browse Books**합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5.  <span data-ttu-id="35d92-143">특정 책을 구매 하려면 목록에서 책을 선택 하 고 클릭 **Buy Book**합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="35d92-144">응용 프로그램이 시작되고 Windows 인증과 HomeRealm 보안 토큰 서비스를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="35d92-145">이 샘플은 사용자가 가격이 $15 이하인 책을 구입할 수 있도록 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="35d92-146">$15보다 비싼 책을 구입하려고 하면 클라이언트는 Book Store 서비스로부터 액세스 거부 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35d92-147">이 샘플은 구입 후 사용자의 신용 한도를 업데이트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="35d92-148">사용자의 (고정)신용 한도 내에서 책을 반복하여 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="35d92-149">정리하려면</span><span class="sxs-lookup"><span data-stu-id="35d92-149">To clean up</span></span>  
  
1.  <span data-ttu-id="35d92-150">Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-150">Run Cleanup.bat.</span></span> <span data-ttu-id="35d92-151">그러면 설치 과정에 만들어졌던 가상 디렉터리를 삭제하며 설치되었던 인증서도 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35d92-152">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="35d92-153">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="35d92-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35d92-154">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="35d92-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35d92-155">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35d92-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
  
## <a name="see-also"></a><span data-ttu-id="35d92-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35d92-156">See Also</span></span>
