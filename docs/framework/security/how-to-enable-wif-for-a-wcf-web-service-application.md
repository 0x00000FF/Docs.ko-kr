---
title: '방법: WCF 웹 서비스 응용 프로그램에 WIF 사용'
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 71897299d68c2f0e43def8e70730ea456d6e9e24
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45678984"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a><span data-ttu-id="e98a3-102">방법: WCF 웹 서비스 응용 프로그램에 WIF 사용</span><span class="sxs-lookup"><span data-stu-id="e98a3-102">How To: Enable WIF for a WCF Web Service Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="e98a3-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="e98a3-103">Applies To</span></span>  
  
-   <span data-ttu-id="e98a3-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="e98a3-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="e98a3-105">Microsoft® Windows® Communication Foundation(WCF)</span><span class="sxs-lookup"><span data-stu-id="e98a3-105">Microsoft® Windows® Communication Foundation (WCF)</span></span>  
  
## <a name="summary"></a><span data-ttu-id="e98a3-106">요약</span><span class="sxs-lookup"><span data-stu-id="e98a3-106">Summary</span></span>  
 <span data-ttu-id="e98a3-107">이 방법 설명에서는 WCF 웹 서비스에서 WIF를 사용하기 위한 자세한 단계별 절차를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-107">This How-To provides detailed step-by-step procedures for enabling WIF in a WCF web service.</span></span> <span data-ttu-id="e98a3-108">또한, 응용 프로그램이 실행될 때 웹 서비스가 클레임을 올바로 표시하는지 확인하기 위해 응용 프로그램을 테스트하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-108">It also provides instructions for how to test the application to verify that the web service is correctly presenting claims when the application is run.</span></span> <span data-ttu-id="e98a3-109">이 방법 설명에 보안 토큰 서비스(STS)를 만들기 위한 자세한 지침은 없으며, 그 대신 ID 및 액세스 도구와 함께 제공되는 개발 STS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="e98a3-110">개발 STS가 실제 인증을 수행하는 것은 아니며, 테스트 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="e98a3-111">이 방법을 완료하려면 ID 및 액세스 도구를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="e98a3-112">[ID 및 액세스 도구](https://go.microsoft.com/fwlink/?LinkID=245849)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="e98a3-113">목차</span><span class="sxs-lookup"><span data-stu-id="e98a3-113">Contents</span></span>  
  
-   <span data-ttu-id="e98a3-114">목표</span><span class="sxs-lookup"><span data-stu-id="e98a3-114">Objectives</span></span>  
  
-   <span data-ttu-id="e98a3-115">개요</span><span class="sxs-lookup"><span data-stu-id="e98a3-115">Overview</span></span>  
  
-   <span data-ttu-id="e98a3-116">단계 요약</span><span class="sxs-lookup"><span data-stu-id="e98a3-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e98a3-117">1단계 - 간단한 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-117">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="e98a3-118">2단계 - WCF 서비스용 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-118">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="e98a3-119">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="e98a3-119">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="e98a3-120">목표</span><span class="sxs-lookup"><span data-stu-id="e98a3-120">Objectives</span></span>  
  
-   <span data-ttu-id="e98a3-121">발행된 토큰을 요구하는 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-121">Create a WCF service that requires issued tokens</span></span>  
  
-   <span data-ttu-id="e98a3-122">STS로부터 토큰을 요청하고 WCF 서비스로 토큰을 전달하는 WCF 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-122">Create a WCF client that requests a token from an STS and passes it to the WCF service</span></span>  
  
## <a name="overview"></a><span data-ttu-id="e98a3-123">개요</span><span class="sxs-lookup"><span data-stu-id="e98a3-123">Overview</span></span>  
 <span data-ttu-id="e98a3-124">이 방법은 WCF 서비스를 개발할 때 개발자가 페더레이션 인증을 사용할 수 있는 방법을 보여주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-124">This How-To is intended to demonstrate how a developer can use federated authentication when developing WCF services.</span></span> <span data-ttu-id="e98a3-125">WCF 서비스에서 페더레이션을 사용할 때의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-125">Some of the benefits of using federation in WCF services include:</span></span>  
  
1.  <span data-ttu-id="e98a3-126">WCF 서비스 코드에서 인증 논리 제외</span><span class="sxs-lookup"><span data-stu-id="e98a3-126">Factoring authentication logic out of WCF service code</span></span>  
  
2.  <span data-ttu-id="e98a3-127">기존 ID 관리 솔루션 재사용</span><span class="sxs-lookup"><span data-stu-id="e98a3-127">Re-using existing identity management solutions</span></span>  
  
3.  <span data-ttu-id="e98a3-128">다른 ID 솔루션과의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="e98a3-128">Interoperability with other identity solutions</span></span>  
  
4.  <span data-ttu-id="e98a3-129">미래 변화에 대한 유연성과 탄력성</span><span class="sxs-lookup"><span data-stu-id="e98a3-129">Flexibility and resilience to future changes</span></span>  
  
 <span data-ttu-id="e98a3-130">WIF와 관련 ID 및 액세스 도구는 다음 단계에서 설명하는 바와 같이 페더레이션된 인증을 사용하여 WCF 서비스를 더욱 쉽게 개발하고 테스트할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-130">WIF and the associated Identity and Access tool make it easier to develop and test a WCF service using federated authentication, as the following steps demonstrate.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="e98a3-131">단계 요약</span><span class="sxs-lookup"><span data-stu-id="e98a3-131">Summary of Steps</span></span>  
  
-   <span data-ttu-id="e98a3-132">1단계 - 간단한 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-132">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="e98a3-133">2단계 - WCF 서비스용 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-133">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="e98a3-134">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="e98a3-134">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-wcf-service"></a><span data-ttu-id="e98a3-135">1단계 - 간단한 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-135">Step 1 – Create a Simple WCF Service</span></span>  
 <span data-ttu-id="e98a3-136">이 단계에서는 ID 및 액세스 도구에 포함되어 있는 개발 STS를 사용하는 새 WCF 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-136">In this step, you will create a new WCF service that uses the Development STS that is included with the Identity and Access tool.</span></span>  
  
#### <a name="to-create-a-simple-wcf-service"></a><span data-ttu-id="e98a3-137">간단한 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e98a3-137">To create a simple WCF service</span></span>  
  
1.  <span data-ttu-id="e98a3-138">관리자로 승격된 모드에서 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-138">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="e98a3-139">Visual Studio에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-139">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="e98a3-140">**새 프로젝트** 창에서 **WCF 서비스 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-140">In the **New Project** window, click **WCF Service Application**.</span></span>  
  
4.  <span data-ttu-id="e98a3-141">**이름**에서 `TestService`를 입력하고 **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-141">In **Name**, enter `TestService` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="e98a3-142">**솔루션 탐색기**에서 **TestService** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **ID 및 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-142">Right-click the **TestService** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="e98a3-143">**ID 및 액세스** 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-143">The **Identity and Access** window appears.</span></span> <span data-ttu-id="e98a3-144">**공급자**에서 **로컬 개발 STS로 응용 프로그램 테스트**를 선택한 다음 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-144">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span> <span data-ttu-id="e98a3-145">ID 및 액세스 도구는 *Web.config* 파일에 구성 요소를 추가하여 WIF를 사용하고 로컬 개발 STS(**LocalSTS**)로 인증을 아웃소싱하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-145">The Identity and Access Tool configures the service to use WIF and to outsource authentication to the local development STS (**LocalSTS**) by adding configuration elements to the *Web.config* file.</span></span>  
  
7.  <span data-ttu-id="e98a3-146">*Service1.svc.cs* 파일에서 **System.Security.Claims** 네임스페이스에 대한 `using` 지시문을 추가하고 기존 코드를 다음으로 바꾼 다음 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-146">In the *Service1.svc.cs* file, add a `using` directive for the **System.Security.Claims** namespace and replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     <span data-ttu-id="e98a3-147">`ComputeResponse` 메서드는 **LocalSTS**가 발행하는 다양한 클레임의 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-147">The `ComputeResponse` method displays the properties of various claims that are issued by **LocalSTS**.</span></span>  
  
8.  <span data-ttu-id="e98a3-148">*IService1.cs* 파일에서 기존 코드를 다음으로 바꾼 다음 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-148">In the *IService1.cs* file, replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. <span data-ttu-id="e98a3-149">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-149">Build the project.</span></span>  
  
10. <span data-ttu-id="e98a3-150">**Ctrl-F5** 키를 눌러 디버거를 시작하지 않고 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-150">Press **Ctrl-F5** to run the service without starting the debugger.</span></span> <span data-ttu-id="e98a3-151">서비스를 위한 웹 페이지가 열려야 하고 알림 영역(시스템 트레이)을 보고 **LocalSTS**가 실행 중인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-151">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e98a3-152">다음 단계에서 클라이언트 응용 프로그램에 서비스 참조를 추가할 때 **TestService**와 **LocalSTS**가 모두 실행 중이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-152">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client application in the next step.</span></span>  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a><span data-ttu-id="e98a3-153">2단계 - WCF 서비스용 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="e98a3-153">Step 2 – Create a Client Application for the WCF Service</span></span>  
 <span data-ttu-id="e98a3-154">이 단계에서는 개발 STS를 사용하여 이전 단계에서 만든 WCF 서비스로 인증하는 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-154">In this step, you will create a console application that uses the Development STS to authenticate with the WCF service you created in the previous step.</span></span>  
  
#### <a name="to-create-a-client-application"></a><span data-ttu-id="e98a3-155">클라이언트 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e98a3-155">To create a client application</span></span>  
  
1.  <span data-ttu-id="e98a3-156">Visual Studio에서 솔루션을 마우스 오른쪽 단추로 클릭하고, **추가**, **새 프로젝트**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-156">In Visual Studio, right-click on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="e98a3-157">**새 프로젝트 추가** 창의 **Visual C#** 템플릿 목록에서 **콘솔 응용 프로그램**을 선택하고, `Client`를 입력한 다음, **확인**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-157">In the **Add New Project** window, select **Console Application** from the **Visual C#** templates list, enter `Client`, and then press **OK**.</span></span> <span data-ttu-id="e98a3-158">새 프로젝트가 솔루션 폴더에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-158">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="e98a3-159">**클라이언트** 프로젝트에서 **참조**를 마우스 오른쪽 단추로 클릭한 다음 **서비스 참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-159">Right-click on **References** under the **Client** project, and then click **Add Service Reference**.</span></span>  
  
4.  <span data-ttu-id="e98a3-160">**서비스 참조 추가** 창에서 **검색** 단추의 드롭다운 화살표를 클릭하고 **솔루션의 서비스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-160">In the **Add Service Reference** window, click the drop-down arrow on the **Discover** button and click **Services in Solution**.</span></span> <span data-ttu-id="e98a3-161">**주소**에는 앞서 만든 WCF 서비스가 자동으로 채워지고 **네임스페이스**는 **ServiceReference1**로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-161">The **Address** will automatically populate with the WCF service you created earlier, and the **Namespace** will be set to **ServiceReference1**.</span></span> <span data-ttu-id="e98a3-162">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-162">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e98a3-163">클라이언트에 서비스 참조를 추가할 때 **TestService**와 **LocalSTS**가 모두 실행 중이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-163">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client.</span></span>  
  
5.  <span data-ttu-id="e98a3-164">Visual Studio는 WCF 서비스를 위한 프록시 클래스를 생성하고 필요한 참조 정보를 모두 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-164">Visual Studio will generate proxy classes for the WCF service, and add all of the necessary reference information.</span></span> <span data-ttu-id="e98a3-165">또한, *App.config* 파일에 요소를 추가하여 클라이언트가 STS에서 토큰을 받아 서비스에 인증하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-165">It will also add elements to the *App.config* file to configure the client to get a token from the STS to authenticate with the service.</span></span> <span data-ttu-id="e98a3-166">이 프로세스가 완료되면 **Program.cs** 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-166">When this process is finished, the **Program.cs** file will open.</span></span> <span data-ttu-id="e98a3-167">**System.ServiceModel**에 대한 `using` 지시문과 **Client.ServiceReference1**에 대한 다른 지시문을 추가하고, **Main** 메서드를 다음 코드로 바꾼 다음, 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-167">Add a `using` directive for **System.ServiceModel** and another for **Client.ServiceReference1**, replace the **Main** method with the following code, then save the file:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  <span data-ttu-id="e98a3-168">*App.config* 파일을 열고, 다음 XML을 `<system.serviceModel>` 요소 아래의 첫 번째 자식 요소로 추가한 다음, 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-168">Open the *App.config* file and add the following XML as the first child element under the `<system.serviceModel>` element, then save the file:</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     <span data-ttu-id="e98a3-169">이렇게 하면 인증서 유효성 검사를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-169">This disables certificate validation.</span></span>  
  
7.  <span data-ttu-id="e98a3-170">**TestService** 솔루션을 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-170">Right-click the **TestService** solution and click on **Set StartUp Projects**.</span></span> <span data-ttu-id="e98a3-171">**시작 프로젝트** 속성 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-171">The **Startup Project** property page opens.</span></span> <span data-ttu-id="e98a3-172">**시작 프로젝트** 속성 페이지에서 **여러 개의 시작 프로젝트**를 선택한 다음, 각 프로젝트에 대한 **작업** 필드를 클릭하고, 드롭다운 메뉴에서 **시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-172">In the **Startup Project** property page, select **Multiple startup projects** then click in the **Action** field for each project and select **Start** from the drop-down menu.</span></span> <span data-ttu-id="e98a3-173">**확인**을 클릭하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-173">Click **OK** to save the settings.</span></span>  
  
8.  <span data-ttu-id="e98a3-174">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-174">Build the solution.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="e98a3-175">3단계 - 솔루션 테스트</span><span class="sxs-lookup"><span data-stu-id="e98a3-175">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="e98a3-176">이 단계에서 WIF를 사용하는 WCF 응용 프로그램을 테스트하고 클레임이 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-176">In this step you will test your WIF-enabled WCF application and verify that claims are presented.</span></span>  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a><span data-ttu-id="e98a3-177">클레임에 대해 WIF를 사용하는 WCF 응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="e98a3-177">To test your WIF-enabled WCF application for claims</span></span>  
  
1.  <span data-ttu-id="e98a3-178">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-178">Press **F5** to build and run the application.</span></span> <span data-ttu-id="e98a3-179">콘솔 창과 서비스를 호출하려면 Enter 키를 누르고, **응용 프로그램을 종료하려면 다른 키를 누르세요.** 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-179">You should be presented with a console window, and the following text: **Press Enter key to invoke service, any other key to quit application:**</span></span>  
  
2.  <span data-ttu-id="e98a3-180">**Enter** 키를 누르면 콘솔에 다음 클레임 정보가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-180">Press **Enter**, and the following claims information should appear in the console:</span></span>  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e98a3-181">**Enter** 키를 누르기 전에 **TestService**와 **LocalSTS**가 모두 실행 중이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-181">Both **TestService** and **LocalSTS** must be running before you press **Enter**.</span></span> <span data-ttu-id="e98a3-182">서비스를 위한 웹 페이지가 열려야 하고 알림 영역(시스템 트레이)을 보고 **LocalSTS**가 실행 중인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-182">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
3.  <span data-ttu-id="e98a3-183">이러한 클레임이 콘솔에 나타나는 경우, WCF 서비스에서 클레임을 표시하도록 STS 인증에 성공한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e98a3-183">If these claims appear in the console, you have successfully authenticated with the STS to display claims from the WCF service.</span></span>
