---
title: Windows 10에 .NET Framework 설치
description: Windows 10 또는 Windows Server 2016에서 .NET Framework를 설치하는 방법을 알아봅니다.
author: rlander
ms.author: mairaw
ms.date: 04/10/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 6db1a3f5fd2011a13a28551a38b319995039ab38
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153615"
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a><span data-ttu-id="3398f-103">Windows 10 및 Windows Server 2016에 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="3398f-103">Install the .NET Framework on Windows 10 and Windows Server 2016</span></span>

<span data-ttu-id="3398f-104">Windows에서 많은 응용 프로그램을 실행하는 데 .NET Framework가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-104">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="3398f-105">이 문서의 지침은 필요한 .NET Framework 버전을 설치하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-105">The instructions in this article should help you install the .NET Framework versions that you need.</span></span> <span data-ttu-id="3398f-106">[.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255)는 사용 가능한 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-106">The [.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) is the latest available version.</span></span>

<span data-ttu-id="3398f-107">응용 프로그램을 실행한 후 컴퓨터에 다음과 같은 대화 상자가 표시되어 이 페이지를 방문했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-107">You may have arrived on this page after trying to run an application and seeing a dialog on your machine similar to the following one:</span></span>

![이 응용 프로그램을 시작할 수 없습니다.](./media/this-application-could-not-be-started.png)

## <a name="net-framework-472"></a><span data-ttu-id="3398f-109">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="3398f-109">.NET Framework 4.7.2</span></span>

<span data-ttu-id="3398f-110">.NET Framework 4.7.2에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-110">The .NET Framework 4.7.2 is included with:</span></span>

* [<span data-ttu-id="3398f-111">Windows 10 2018년 10월 업데이트</span><span class="sxs-lookup"><span data-stu-id="3398f-111">Windows 10 October 2018 Update</span></span>](https://support.microsoft.com/help/4028685/windows-10-get-the-update)

* [<span data-ttu-id="3398f-112">Windows 10 2018년 4월 업데이트</span><span class="sxs-lookup"><span data-stu-id="3398f-112">Windows 10 April 2018 Update</span></span>](https://www.microsoft.com/software-download/windows10)

> [!div class="button"]
> [<span data-ttu-id="3398f-113">.NET Framework 4.7.2 다운로드</span><span class="sxs-lookup"><span data-stu-id="3398f-113">Download .NET Framework 4.7.2</span></span>](https://www.microsoft.com/net/download/thank-you/net472?utm_source=ms-docs&utm_medium=referral)

<span data-ttu-id="3398f-114">[.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255)는 .NET Framework 4.0~4.7.1용으로 빌드된 응용 프로그램을 실행하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-114">The [.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) can be used to run applications built for the .NET Framework 4.0 through 4.7.1.</span></span>

<span data-ttu-id="3398f-115">다음에 [.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-115">You can install the [.NET Framework 4.7.2](https://go.microsoft.com/fwlink/?LinkID=863255) on:</span></span>

* <span data-ttu-id="3398f-116">Windows 10 가을 작성자 업데이트(버전 1709)</span><span class="sxs-lookup"><span data-stu-id="3398f-116">Windows 10 Fall Creators Update (version 1709)</span></span>
* <span data-ttu-id="3398f-117">Windows 10 Creators Update(버전 1703)</span><span class="sxs-lookup"><span data-stu-id="3398f-117">Windows 10 Creators Update (version 1703)</span></span>
* <span data-ttu-id="3398f-118">Windows 10 1주년 업데이트(버전 1607)</span><span class="sxs-lookup"><span data-stu-id="3398f-118">Windows 10 Anniversary Update (version 1607)</span></span>
* <span data-ttu-id="3398f-119">Windows Server, 버전 1709</span><span class="sxs-lookup"><span data-stu-id="3398f-119">Windows Server, version 1709</span></span>
* <span data-ttu-id="3398f-120">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3398f-120">Windows Server 2016</span></span>

<span data-ttu-id="3398f-121">.NET Framework 4.7.2는 다음에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-121">The .NET Framework 4.7.2 is not supported on:</span></span>

* <span data-ttu-id="3398f-122">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="3398f-122">Windows 10 1507</span></span>
* <span data-ttu-id="3398f-123">Windows 10 1511</span><span class="sxs-lookup"><span data-stu-id="3398f-123">Windows 10 1511</span></span>

<span data-ttu-id="3398f-124">Windows 10 1507 또는 1511을 사용 중인 경우 .NET Framework 4.7.2를 설치하려면 먼저 이후 Windows 10 버전으로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-124">If you're using Windows 10 1507 or 1511 and you want to install the .NET Framework 4.7.2, you first need to upgrade to a later Windows 10 version.</span></span>

## <a name="net-framework-462"></a><span data-ttu-id="3398f-125">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="3398f-125">.NET Framework 4.6.2</span></span>

<span data-ttu-id="3398f-126">[.NET Framework 4.6.2](https://www.microsoft.com/en-us/download/details.aspx?id=53345)는 Windows 10 1507 및 1511에서 지원되는 최신 .NET Framework 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-126">The [.NET Framework 4.6.2](https://www.microsoft.com/en-us/download/details.aspx?id=53345) is the latest supported .NET Framework version on Windows 10 1507 and 1511.</span></span>

<span data-ttu-id="3398f-127">.NET Framework 4.6.2는 .NET Framework 4.0~4.6.2용으로 빌드된 앱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-127">The .NET Framework 4.6.2 supports apps built for the .NET Framework 4.0 through 4.6.2.</span></span>

## <a name="net-framework-35"></a><span data-ttu-id="3398f-128">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="3398f-128">.NET Framework 3.5</span></span>

<span data-ttu-id="3398f-129">지침에 따라 [.NET Framework 3.5를 Windows 10에](dotnet-35-windows-10.md) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-129">Follow the instructions to install the [.NET Framework 3.5 on Windows 10](dotnet-35-windows-10.md).</span></span>

<span data-ttu-id="3398f-130">.NET Framework 3.5는 .NET Framework 1.0~3.5용으로 빌드된 앱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-130">The .NET Framework 3.5 supports apps built for the .NET Framework 1.0 through 3.5.</span></span>

## <a name="additional-information"></a><span data-ttu-id="3398f-131">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3398f-131">Additional information</span></span>

<span data-ttu-id="3398f-132">.NET Framework 4.x 버전은 이전 버전에 대한 내부 업데이트입니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-132">.NET Framework 4.x versions are in-place updates to earlier versions.</span></span> <span data-ttu-id="3398f-133">이는 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-133">That means the following:</span></span>

- <span data-ttu-id="3398f-134">컴퓨터에는 하나의 .NET Framework 4.x 버전만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-134">You can only have one version of the .NET Framework 4.x installed on your machine.</span></span>

- <span data-ttu-id="3398f-135">이후 버전이 이미 설치되어 있으면 컴퓨터에 이전 버전의 .NET Framework를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-135">You cannot install an earlier version of the .NET Framework on your machine if a later version is already installed.</span></span>

- <span data-ttu-id="3398f-136">.NET Framework 4.x 버전은 .NET Framework 4.0~해당 버전용으로 빌드된 응용 프로그램을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-136">4.x versions of the .NET Framework can be used to run applications built for the .NET Framework 4.0 through that version.</span></span> <span data-ttu-id="3398f-137">예를 들어 .NET Framework 4.7은 .NET Framework 4.0~4.7용으로 빌드된 응용 프로그램을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-137">For example, .NET Framework 4.7 can be used to run applications built for the .NET Framework 4.0 through 4.7.</span></span> <span data-ttu-id="3398f-138">최신 버전(.NET Framework 4.7.2)은 4.0으로 시작되는 모든 .NET Framework 버전으로 빌드된 응용 프로그램을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-138">The latest version (the .NET Framework 4.7.2) can be used to run applications built with all versions of the .NET Framework starting with 4.0.</span></span>

<span data-ttu-id="3398f-139">다운로드할 수 있는 모든 .NET Framework 버전 목록은 [.NET 다운로드](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3398f-139">For a list of all the versions of the .NET Framework available to download, see the [.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) page.</span></span>

## <a name="help"></a><span data-ttu-id="3398f-140">도움말</span><span class="sxs-lookup"><span data-stu-id="3398f-140">Help</span></span>

<span data-ttu-id="3398f-141">설치된 .NET Framework의 정확한 버전을 확인할 수 없는 경우 [Microsoft에 지원을 문의](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3398f-141">If you cannot get the correct version of the .NET Framework installed, you can [contact Microsoft for help](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).</span></span>

## <a name="see-also"></a><span data-ttu-id="3398f-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3398f-142">See also</span></span>

<span data-ttu-id="3398f-143">[.NET 다운로드](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) </span><span class="sxs-lookup"><span data-stu-id="3398f-143">[.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) </span></span>  
<span data-ttu-id="3398f-144">[차단된 .NET Framework 설치 및 제거 문제 해결](troubleshoot-blocked-installations-and-uninstallations.md) </span><span class="sxs-lookup"><span data-stu-id="3398f-144">[Troubleshoot blocked .NET Framework installations and uninstallations](troubleshoot-blocked-installations-and-uninstallations.md) </span></span>  
[<span data-ttu-id="3398f-145">개발자용 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="3398f-145">Install the .NET Framework for developers</span></span>](guide-for-developers.md)
