---
title: '방법: WCF Activation 구성 요소 설치 및 구성'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 8b516bb4603f33828069b5356676d8b35dc961d2
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46326100"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="cfc85-102">방법: WCF Activation 구성 요소 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="cfc85-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="cfc85-103">이 항목에서는에 Windows Process Activation Service (WAS 라고도 함)을 설정 하는 데 필요한 단계를 설명 [!INCLUDE[wv](../../../../includes/wv-md.md)] HTTP를 통해 통신 하지 않는 서비스 네트워크 프로토콜을 Windows Communication Foundation (WCF)를 호스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="cfc85-104">다음 단원에서는 이 구성 단계에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-104">The following sections outline the steps for this configuration:</span></span>  
  
-   <span data-ttu-id="cfc85-105">설치 (또는 설치를 확인) WCF activation 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-105">Install (or confirm the installation of) the WCF activation components.</span></span>  
  
-   <span data-ttu-id="cfc85-106">HTTP가 아닌 프로토콜을 지원하도록 WAS를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="cfc85-107">다음 절차에서는 TCP 활성화를 위해 [!INCLUDE[wv](../../../../includes/wv-md.md)]를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="cfc85-108">WAS를 설치 및 구성을 확인 한 후 [방법: WAS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) 여 WAS를 사용 하는 HTTP가 아닌 끝점을 노출 하는 WCF 서비스를 만드는 절차에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="cfc85-109">WCF Non-HTTP Activation 구성 요소를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="cfc85-109">To install the WCF non-HTTP activation components</span></span>  
  
1.  <span data-ttu-id="cfc85-110">클릭 합니다 **시작** 단추를 클릭 한 다음 클릭 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="cfc85-111">클릭 **프로그램**를 클릭 하 고 **프로그램 및 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="cfc85-112">에 **태스크** 메뉴에서 클릭 **설정할 Windows 기능 사용 /** 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4.  <span data-ttu-id="cfc85-113">[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 노드를 찾아서 선택한 다음 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-113">Find the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] node, select and then expand it.</span></span>  
  
5.  <span data-ttu-id="cfc85-114">선택 된 **WCF Non-http Activation 구성 요소** 상자 하 고 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="cfc85-115">TCP 활성화를 지원하도록 WAS를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="cfc85-115">To configure the WAS to support TCP activation</span></span>  
  
1.  <span data-ttu-id="cfc85-116">net.tcp 활성화를 지원하려면 먼저 기본 웹 사이트를 net.tcp 포트에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="cfc85-117">이 작업은 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 관리 도구 집합과 함께 설치되는 Appcmd.exe를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-117">You can do this by using Appcmd.exe, which is installed with the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] management toolset.</span></span> <span data-ttu-id="cfc85-118">관리자 수준 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cfc85-119">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-119">This command is a single line of text.</span></span> <span data-ttu-id="cfc85-120">이 명령은 임의의 호스트 이름을 사용하여 TCP 포트 808에서 수신 대기하는 기본 웹 사이트에 net.tcp 사이트 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2.  <span data-ttu-id="cfc85-121">사이트 내의 모든 응용 프로그램이 공통된 net.tcp 바인딩을 공유하지만 각 응용 프로그램에서 개별적으로 net.tcp 지원을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="cfc85-122">응용 프로그램에 대해 net.tcp를 사용하도록 설정하려면 관리자 수준 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cfc85-123">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-123">This command is a single line of text.</span></span> <span data-ttu-id="cfc85-124">이 명령을 사용 하는 /\<*WCF 응용 프로그램*> 응용 프로그램에 모두 사용 하 여 액세스할 수 `http://localhost/<WCF Application>` 고 `net.tcp://localhost/<WCF Application>`입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>
  
     <span data-ttu-id="cfc85-125">이 샘플에 대해 추가한 net.tcp 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="cfc85-126">편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 RemoveNetTcpSiteBinding.cmd라는 배치 파일에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="cfc85-127">관리자 수준 명령 프롬프트 창에서 다음 명령을 실행하여 사용하도록 설정된 프로토콜 목록에서 net.tcp를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="cfc85-128">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-128">This command is a single line of text.</span></span>  
  
    2.  <span data-ttu-id="cfc85-129">고급 명령 프롬프트 창에서 다음 명령을 실행하여 net.tcp 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="cfc85-130">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="cfc85-131">사용하도록 설정된 프로토콜 목록에서 net.tcp를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="cfc85-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1.  <span data-ttu-id="cfc85-132">사용하도록 설정된 프로토콜 목록에서 net.tcp를 제거하려면 관리자 수준 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cfc85-133">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="cfc85-134">net.tcp 사이트 바인딩을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="cfc85-134">To remove the net.tcp site binding</span></span>  
  
1.  <span data-ttu-id="cfc85-135">net.tcp 사이트 바인딩을 제거하려면 관리자 수준 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cfc85-136">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc85-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc85-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfc85-137">See Also</span></span>  
 [<span data-ttu-id="cfc85-138">TCP 활성화</span><span class="sxs-lookup"><span data-stu-id="cfc85-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [<span data-ttu-id="cfc85-139">MSMQ 활성화</span><span class="sxs-lookup"><span data-stu-id="cfc85-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [<span data-ttu-id="cfc85-140">NamedPipe 활성화</span><span class="sxs-lookup"><span data-stu-id="cfc85-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [<span data-ttu-id="cfc85-141">Windows Server App Fabric 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="cfc85-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
