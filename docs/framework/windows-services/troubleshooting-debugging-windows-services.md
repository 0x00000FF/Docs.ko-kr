---
title: "문제 해결: Windows 서비스 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="3af00-102">문제 해결: Windows 서비스 디버깅</span><span class="sxs-lookup"><span data-stu-id="3af00-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="3af00-103">Windows 서비스 응용 프로그램, 서비스를 디버그할 때 및 **Windows 서비스 관리자** 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af00-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="3af00-104">**Service Manager** 호출 하 여 서비스를 시작한는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 30 초 정도 대기는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af00-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="3af00-105">이 메서드가 반환 하지 않으면, 관리자는 오류를 보여 줍니다 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3af00-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="3af00-106">디버그할 때는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드에 설명 된 대로 [하는 방법: Windows 서비스 응용 프로그램 디버그](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), 30 초 그러는 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af00-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="3af00-107">중단점을 배치 하는 경우는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드 30 초 내에 것 단계별로 실행 하지 않는 하 고, 관리자 서비스를 시작 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3af00-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af00-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3af00-108">See Also</span></span>  
 [<span data-ttu-id="3af00-109">방법: Windows 서비스 응용 프로그램 디버그</span><span class="sxs-lookup"><span data-stu-id="3af00-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="3af00-110">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="3af00-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
