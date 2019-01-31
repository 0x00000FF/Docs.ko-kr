---
title: '문제 해결: 서비스 애플리케이션이 설치되지 않음'
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: 998c7a3f5ca405b3bd66b877d027126f6c76cc15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494420"
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="fa6d2-102">문제 해결: 서비스 애플리케이션이 설치되지 않음</span><span class="sxs-lookup"><span data-stu-id="fa6d2-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="fa6d2-103">서비스 애플리케이션이 올바로 설치되지 않으면 서비스 클래스의 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성이 해당 서비스의 설치 관리자에 표시된 값과 동일하게 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d2-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="fa6d2-104">서비스가 올바로 설치되려면 이 값이 두 인스턴스 모두에서 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d2-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa6d2-105">설치 로그를 확인하여 설치 프로세스에 대한 피드백을 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d2-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="fa6d2-106">같은 이름의 다른 서비스가 이미 설치되어 있는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d2-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="fa6d2-107">서비스 이름이 고유해야만 설치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6d2-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6d2-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa6d2-108">See also</span></span>
- [<span data-ttu-id="fa6d2-109">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="fa6d2-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
