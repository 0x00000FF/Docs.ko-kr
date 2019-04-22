---
title: WPF 호스트(PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 586d306d0f375241c9382e1e24cf1af75b990ba9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122865"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="19b6e-102">WPF 호스트(PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="19b6e-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="19b6e-103">Windows Presentation Foundation (WPF) 호스트 (PresentationHost.exe)은 응용 프로그램입니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 호환 브라우저에서 호스팅 되도록 응용 프로그램 (포함 하 여 [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] 이상).</span><span class="sxs-lookup"><span data-stu-id="19b6e-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="19b6e-104">기본적으로 Windows Presentation Foundation (WPF) 호스트 셸로 등록 하 고 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 처리기에 대 한 브라우저에서 호스팅된 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 콘텐츠를 포함 하는:</span><span class="sxs-lookup"><span data-stu-id="19b6e-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="19b6e-105">느슨하게 압축되지 않은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일(.xaml).</span><span class="sxs-lookup"><span data-stu-id="19b6e-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="19b6e-106">(.xbap).</span><span class="sxs-lookup"><span data-stu-id="19b6e-106">(.xbap).</span></span>  
  
 <span data-ttu-id="19b6e-107">Windows Presentation Foundation (WPF) 호스트 이러한 형식의 파일:</span><span class="sxs-lookup"><span data-stu-id="19b6e-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
-   <span data-ttu-id="19b6e-108">등록 된 시작 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] Windows Presentation Foundation (WPF) 콘텐츠를 호스트 하는 처리기.</span><span class="sxs-lookup"><span data-stu-id="19b6e-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
-   <span data-ttu-id="19b6e-109">필요한 올바른 버전을 로드 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 및 Windows Presentation Foundation (WPF) 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
-   <span data-ttu-id="19b6e-110">배포 영역에 대해 적절한 권한 수준이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="19b6e-111">이 항목에서는 PresentationHost.exe에서 사용할 수 있는 명령줄 매개 변수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="19b6e-112">용도</span><span class="sxs-lookup"><span data-stu-id="19b6e-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="19b6e-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19b6e-113">Parameters</span></span>  
  
|<span data-ttu-id="19b6e-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19b6e-114">Parameter</span></span>|<span data-ttu-id="19b6e-115">설명</span><span class="sxs-lookup"><span data-stu-id="19b6e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19b6e-116">filename</span><span class="sxs-lookup"><span data-stu-id="19b6e-116">filename</span></span>|<span data-ttu-id="19b6e-117">활성화할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-117">The path of the file to be activated.</span></span> <span data-ttu-id="19b6e-118">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="19b6e-119">-debug</span><span class="sxs-lookup"><span data-stu-id="19b6e-119">-debug</span></span>|<span data-ttu-id="19b6e-120">애플리케이션을 활성화할 때 저장소에서 커밋하거나 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="19b6e-121">이는 로컬 파일이 활성화된 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="19b6e-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="19b6e-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="19b6e-123">지정된 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]에서 배포된 것처럼 애플리케이션이 디버깅되어야 함을 PresentationHost.exe에 알리기 위해 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 값과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="19b6e-124">이를 통해 배포 영역과 원본 사이트가 모두 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="19b6e-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="19b6e-125">-embedding</span></span>|<span data-ttu-id="19b6e-126">OLE에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-126">Required by OLE.</span></span> <span data-ttu-id="19b6e-127">`-event` 또는 `-debug` 매개 변수가 지정된 경우 `-embedding` 매개 변수가 내부적으로 설정되기 때문에 해당 매개 변수를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="19b6e-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="19b6e-128">-event \<eventname></span></span>|<span data-ttu-id="19b6e-129">이 이름으로 이벤트를 연 다음 PresentationHost.exe가 초기화되고 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 콘텐츠를 호스팅할 준비가 되면 이 이벤트에 신호를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="19b6e-130">이벤트가 아직 만들어지지 않은 등의 이유로 인해 이벤트를 여는 데 오류가 발생하면 PresentationHost.exe가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="19b6e-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="19b6e-131">-launchApplication \<url></span></span>|<span data-ttu-id="19b6e-132">지정된 URL에서 독립 실행형 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> <span data-ttu-id="19b6e-133">.NET 응용 프로그램과 관련된 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 및 WinINet 보안 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b6e-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="19b6e-134">시나리오</span><span class="sxs-lookup"><span data-stu-id="19b6e-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="19b6e-135">셸 처리기</span><span class="sxs-lookup"><span data-stu-id="19b6e-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="19b6e-136">MIME 처리기</span><span class="sxs-lookup"><span data-stu-id="19b6e-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="19b6e-137">Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="19b6e-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="19b6e-138">영역에서 Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="19b6e-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="19b6e-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="19b6e-139">See also</span></span>

- [<span data-ttu-id="19b6e-140">보안</span><span class="sxs-lookup"><span data-stu-id="19b6e-140">Security</span></span>](../security-wpf.md)
