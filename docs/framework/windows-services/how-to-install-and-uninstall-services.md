---
title: '방법: 서비스 설치 및 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
manager: douge
ms.openlocfilehash: 9d8e84280b5821f8d8df36694198bd85fb8470d4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416910"
---
# <a name="how-to-install-and-uninstall-services"></a><span data-ttu-id="2cbe3-102">방법: 서비스 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="2cbe3-102">How to: Install and Uninstall Services</span></span>
<span data-ttu-id="2cbe3-103">.NET Framework를 사용하여 Windows 서비스를 개발하는 경우에는 명령줄 유틸리티 InstallUtil.exe를 사용하여 서비스 응용 프로그램을 빠르게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-103">If you’re developing a Windows Service by using the .NET Framework, you can quickly install your service application by using a command-line utility called InstallUtil.exe.</span></span> <span data-ttu-id="2cbe3-104">사용자가 설치 및 제거할 수 있는 Windows 서비스를 릴리스하려는 개발자는 InstallShield를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-104">If you’re a developer who wants to release a Windows Service that users can install and uninstall  you should use InstallShield.</span></span> <span data-ttu-id="2cbe3-105">[Windows Installer Deployment](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)(Windows Installer 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-105">See [Windows Installer Deployment](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2cbe3-106">서비스를 컴퓨터에서 제거하려면 이 문서의 단계를 수행하는 대신</span><span class="sxs-lookup"><span data-stu-id="2cbe3-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="2cbe3-107">서비스를 설치한 프로그램 또는 소프트웨어 패키지를 확인하고 제어판에서 **프로그램 추가/제거**를 선택하여 해당 프로그램을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-107">Instead, find out which program or software package installed the service, and then choose **Add/Remove Programs** in Control Panel to uninstall that program.</span></span> <span data-ttu-id="2cbe3-108">대부분의 서비스는 Windows의 필수 요소이므로 제거하는 경우 시스템이 불안정해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="2cbe3-109">이 문서의 단계를 수행하려면 먼저 Windows 서비스에 서비스 설치 관리자를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-109">In order to use the steps in this article, you first need to add a service installer to your Windows Service.</span></span> <span data-ttu-id="2cbe3-110">[Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)(연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-110">See [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="2cbe3-111">Windows 서비스 프로젝트는 F5 키를 눌러 Visual Studio 개발 환경에서 직접 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-111">Windows Service projects cannot be run directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="2cbe3-112">프로젝트를 실행하려면 프로젝트의 서비스를 먼저 설치해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-112">This is because the service in the project must be installed before you can run the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="2cbe3-113">**서버 탐색기**를 시작하여 서비스가 설치 또는 제거되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-113">You can launch **Server Explorer** and verify that your service has been installed or uninstalled.</span></span> <span data-ttu-id="2cbe3-114">자세한 내용은 방법: 서버 탐색기-데이터베이스 탐색기 액세스 및 초기화를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-114">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
### <a name="to-install-your-service-manually"></a><span data-ttu-id="2cbe3-115">서비스를 수동으로 설치하려면</span><span class="sxs-lookup"><span data-stu-id="2cbe3-115">To install your service manually</span></span>  
  
1.  <span data-ttu-id="2cbe3-116">Windows **시작** 메뉴 또는 **시작** 화면에서 **Visual Studio**, **Visual Studio Tools**, **개발자 명령 프롬프트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-116">On the Windows **Start** menu or **Start** screen, choose **Visual Studio** , **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="2cbe3-117">Visual Studio 명령 프롬프트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-117">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="2cbe3-118">프로젝트의 컴파일된 실행 파일이 있는 디렉터리에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="2cbe3-119">프로젝트의 실행 파일을 매개 변수로 사용하여 명령 프롬프트에서 InstallUtil.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-119">Run InstallUtil.exe from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     <span data-ttu-id="2cbe3-120">Visual Studio 명령 프롬프트를 사용하는 경우 InstallUtil.exe가 시스템 경로에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-120">If you’re using the Visual Studio command prompt, InstallUtil.exe should be on the system path.</span></span> <span data-ttu-id="2cbe3-121">그러지 않으면 경로에 InstallUtil.exe를 추가하거나 정규화된 경로를 사용하여 해당 파일을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-121">If not, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="2cbe3-122">이 도구는 .NET Framework와 함께 설치되며 경로는 `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-122">This tool is installed with the .NET Framework, and its path is `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span></span> <span data-ttu-id="2cbe3-123">예를 들어 32비트 버전 .NET Framework 4 또는 4.5.\*의 경우 Windows 설치 디렉터리가 C:\Windows이면 경로는 `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-123">For example, for the 32-bit version of the .NET Framework 4 or 4.5.\*, if your Windows installation directory is C:\Windows, the path is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span> <span data-ttu-id="2cbe3-124">64비트 버전 .NET Framework 4 또는 4.5.\*의 경우 기본 경로는 `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-124">For the 64-bit version of the .NET Framework 4 or 4.5.\*, the default path is `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span></span>  
  
### <a name="to-uninstall-your-service-manually"></a><span data-ttu-id="2cbe3-125">서비스를 수동으로 제거하려면</span><span class="sxs-lookup"><span data-stu-id="2cbe3-125">To uninstall your service manually</span></span>  
  
1.  <span data-ttu-id="2cbe3-126">Windows **시작** 메뉴 또는 **시작** 화면에서 **Visual Studio**, **Visual Studio Tools**, **개발자 명령 프롬프트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-126">On the Windows **Start** menu or **Start** screen, choose **Visual Studio**, **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="2cbe3-127">Visual Studio 명령 프롬프트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-127">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="2cbe3-128">프로젝트의 출력을 매개 변수로 사용하여 명령 프롬프트에서 InstallUtil.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-128">Run InstallUtil.exe from the command prompt with your project's output as a parameter:</span></span>  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  <span data-ttu-id="2cbe3-129">서비스의 실행 파일을 삭제해도 서비스가 레지스트리에 남아 있는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-129">Sometimes, after the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="2cbe3-130">이러한 경우에는 [sc delete](https://technet.microsoft.com/library/cc742045.aspx) 명령을 사용하여 레지스트리에서 서비스 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-130">In that case, use the command [sc delete](https://technet.microsoft.com/library/cc742045.aspx) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbe3-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cbe3-131">See Also</span></span>  
 [<span data-ttu-id="2cbe3-132">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="2cbe3-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="2cbe3-133">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="2cbe3-133">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="2cbe3-134">방법: 서비스 응용 프로그램에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="2cbe3-134">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="2cbe3-135">Installutil.exe(설치 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="2cbe3-135">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)
