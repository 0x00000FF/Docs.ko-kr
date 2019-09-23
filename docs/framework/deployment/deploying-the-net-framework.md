---
title: .NET Framework 배포
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6906ccf5b639d6b90b921b5d471aa723aeb4da78
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052161"
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="bca53-102">.NET Framework 배포</span><span class="sxs-lookup"><span data-stu-id="bca53-102">Deploying the .NET Framework</span></span>
<span data-ttu-id="bca53-103">.NET Framework 설명서의 이 섹션은 애플리케이션과 함께 .NET Framework를 설치하려는 개발자 및 네트워크에서 .NET Framework를 배포하려는 관리자를 위한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-103">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="bca53-104">또한 배포에 관련된 활성화 및 다시 시작 문제와 .NET Framework 설치의 진행 상황을 모니터링하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-104">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bca53-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bca53-105">In This Section</span></span>  
 [<span data-ttu-id="bca53-106">개발자를 위한 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="bca53-106">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)  
 <span data-ttu-id="bca53-107">개발자가 애플리케이션과 함께 .NET Framework를 사용자 컴퓨터에 설치할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-107">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="bca53-108">관리자를 위한 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="bca53-108">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)  
 <span data-ttu-id="bca53-109">시스템 관리자가 SCCM(System Center Configuration Manager)을 사용하여 .NET Framework 및 해당 시스템 종속성을 네트워크 전체에 배포할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-109">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>  
  
 [<span data-ttu-id="bca53-110">.NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기</span><span class="sxs-lookup"><span data-stu-id="bca53-110">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)  
 <span data-ttu-id="bca53-111">최대한 다시 시작을 방지하는 다시 시작 관리자 및 .NET Framework를 설치하는 애플리케이션이 다시 시작 관리자를 활용할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-111">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="bca53-112">방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기</span><span class="sxs-lookup"><span data-stu-id="bca53-112">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="bca53-113">설치 진행 상황을 자체적으로 표시하면서 .NET Framework 설치 프로세스를 자동으로 시작하고 추적하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-113">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="bca53-114">.NET Framework 초기화 오류: 사용자 환경 관리</span><span class="sxs-lookup"><span data-stu-id="bca53-114">.NET Framework Initialization Errors: Managing the User Experience</span></span>](initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="bca53-115">.NET Framework 애플리케이션에 잘못되거나 사용자 컴퓨터에 설치되지 않은 CLR 버전이 필요한 경우 발생하는 문제, 이러한 오류를 해결하는 방법 및 사용자에게 표시되는 오류 메시지를 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-115">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="bca53-116">방법: CLR 활성화 문제 디버깅</span><span class="sxs-lookup"><span data-stu-id="bca53-116">How to: Debug CLR Activation Issues</span></span>](how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="bca53-117">CLR 활성화 로그를 보고 디버그하여 애플리케이션을 올바른 버전의 CLR과 함께 실행할 때 발생할 수 있는 문제를 해결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bca53-117">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca53-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bca53-118">See also</span></span>

- [<span data-ttu-id="bca53-119">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="bca53-119">Development Guide</span></span>](../development-guide.md)
