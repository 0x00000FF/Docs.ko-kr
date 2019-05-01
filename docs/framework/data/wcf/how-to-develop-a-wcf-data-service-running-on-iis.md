---
title: '방법: IIS에서 실행되는 WCF Data Service 개발'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 74c31c748dd3483aa87afb2c9a7d926965c9f1ed
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "63773938"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="554b4-102">방법: IIS에서 실행 되는 WCF 데이터 서비스 개발</span><span class="sxs-lookup"><span data-stu-id="554b4-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="554b4-103">이 항목에서는 WCF Data Services를 사용 하 여 인터넷 정보 서비스 (IIS)에서 실행 중인 ASP.NET 웹 응용 프로그램에서 호스트 되는 Northwind 샘플 데이터베이스를 기반으로 하는 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-103">This topic shows how to use WCF Data Services to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="554b4-104">ASP.NET Development Server에서 실행 되는 ASP.NET 웹 응용 프로그램으로 동일한 Northwind 데이터 서비스를 만드는 방법의 예제를 참조 합니다 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="554b4-105">Northwind 데이터 서비스를 만들려면 로컬 컴퓨터에 Northwind 샘플 데이터베이스를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="554b4-106">이 샘플 데이터베이스를 다운로드하려면 [SQL Server용 샘플 데이터베이스](https://go.microsoft.com/fwlink/?linkid=24758)다운로드 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="554b4-106">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

<span data-ttu-id="554b4-107">이 항목에서는 Entity Framework 공급자를 사용하여 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="554b4-108">다른 데이터 서비스 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-108">Other data services providers are available.</span></span> <span data-ttu-id="554b4-109">자세한 내용은 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="554b4-110">서비스를 만든 후 데이터 서비스 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="554b4-111">자세한 내용은 [방법: 데이터 서비스에 액세스할 수 있도록](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="554b4-112">IIS에서 실행 되는 ASP.NET 웹 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="554b4-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="554b4-113">Visual Studio에서에 **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="554b4-114">에 **새 프로젝트** 대화 상자를 선택 합니다 **설치 됨** > [**Visual C#**  또는 **Visual Basic**] > **웹**  범주입니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="554b4-115">선택 된 **ASP.NET 웹 응용 프로그램** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="554b4-115">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="554b4-116">입력 `NorthwindService` 프로젝트의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="554b4-117">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-117">Click **OK**.</span></span>

6. <span data-ttu-id="554b4-118">에 **프로젝트** 메뉴에서 **NorthwindService 속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="554b4-119">선택 된 **웹** 탭을 선택한 후 **사용 하 여 로컬 IIS 웹 서버**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="554b4-120">클릭 **가상 디렉터리 만들기** 을 클릭 한 다음 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="554b4-121">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="554b4-122">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="554b4-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="554b4-123">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="554b4-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="554b4-124">이렇게 하면 WCF(Windows Communication Foundation)가 컴퓨터에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="554b4-125">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="554b4-126">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="554b4-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="554b4-127">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="554b4-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="554b4-128">이렇게 하면 WCF가 컴퓨터에 설치된 후 IIS가 제대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="554b4-129">또한 IIS를 다시 시작해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="554b4-130">ASP.NET 응용 프로그램이 IIS7에서 실행되는 경우 다음 단계도 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="554b4-131">IIS 관리자를 열고 아래의 PhotoService 응용 프로그램을 이동할 **기본 웹 사이트**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="554b4-132">**기능 보기**를 두 번 클릭 **인증**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="554b4-133">에 **Authentication** 페이지에서 **익명 인증**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="554b4-134">에 **동작** 창 클릭 **편집** 보안을 설정 하려면 사용자는 익명 사용자가 사이트에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="554b4-135">에 **익명 인증 자격 증명 편집** 대화 상자에서 **응용 프로그램 풀 id**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="554b4-136">Network Service 계정을 사용하는 경우 해당 계정과 연결된 모든 내부 네트워크 액세스 권한이 익명 사용자에게 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="554b4-137">SQL Server Management Studio, sqlcmd.exe 유틸리티 또는 Visual Studio의 Transact-SQL 편집기를 사용하여 Northwind 데이터베이스가 연결된 SQL Server 인스턴스에 대해 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="554b4-138">이렇게 하면 IIS를 실행하는 데 사용되는 Windows 계정에 대한 로그인이 SQL Server 인스턴스에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="554b4-139">이에 따라 IIS에서 SQL Server 인스턴스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="554b4-140">Northwind 데이터베이스가 연결된 상태에서 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    <span data-ttu-id="554b4-141">이렇게 하면 새 로그인에 권한이 부여되어 IIS에서 Northwind 데이터베이스에 있는 데이터를 읽고 Northwind 데이터베이스에 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="554b4-142">데이터 모델 정의</span><span class="sxs-lookup"><span data-stu-id="554b4-142">Define the data model</span></span>

1. <span data-ttu-id="554b4-143">**솔루션 탐색기**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **추가** > **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="554b4-144">에 **새 항목 추가** 대화 상자에서 **ADO.NET Entity Data Model**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="554b4-145">데이터 모델의 이름에 대 한 입력 `Northwind.edmx`합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="554b4-146">엔터티 데이터 모델 마법사에서 선택 **데이터베이스에서 생성**를 클릭 하 고 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="554b4-147">다음 단계 중 하나를 수행 하 여 데이터 모델 데이터베이스에 연결 하 고 클릭 **다음**:</span><span class="sxs-lookup"><span data-stu-id="554b4-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="554b4-148">데이터베이스 연결이 이미 구성 되어 없으면 클릭 **새 연결** 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="554b4-149">자세한 내용은 [방법: SQL Server 데이터베이스에 연결을 만들](https://go.microsoft.com/fwlink/?LinkId=123631)합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-149">For more information, see [How to: Create Connections to SQL Server Databases](https://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="554b4-150">이 SQL Server 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="554b4-151">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="554b4-151">\- or -</span></span>

    - <span data-ttu-id="554b4-152">Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="554b4-153">마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="554b4-154">**마침** 을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="554b4-155">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="554b4-155">Create the data service</span></span>

1. <span data-ttu-id="554b4-156">**솔루션 탐색기**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **추가** > **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="554b4-157">에 **새 항목 추가** 대화 상자에서 **WCF 데이터 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Visual Studio 2015에서 WCF 데이터 서비스 항목 템플릿](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="554b4-159">합니다 **WCF 데이터 서비스** 서식 파일은 Visual Studio 2015 하지만 되지에 Visual Studio 2017에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="554b4-160">서비스의 이름에 대 한 입력 `Northwind`합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="554b4-161">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="554b4-162">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="554b4-163">**솔루션 탐색기**, 서비스 이름, Northwind 및 확장에. svc.cs 또는. svc.vb 합니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="554b4-164">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="554b4-165">클래스 정의는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="554b4-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="554b4-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="554b4-166">See also</span></span>

- [<span data-ttu-id="554b4-167">서비스로 데이터 노출</span><span class="sxs-lookup"><span data-stu-id="554b4-167">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
