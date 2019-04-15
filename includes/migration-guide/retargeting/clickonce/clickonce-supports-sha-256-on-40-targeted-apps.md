---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234488"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="a06d0-101">ClickOnce가 4.0 대상 앱에서 SHA-256 지원</span><span class="sxs-lookup"><span data-stu-id="a06d0-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a06d0-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a06d0-102">Details</span></span>|<span data-ttu-id="a06d0-103">이전에 SHA-256으로 서명된 인증서가 있는 ClickOnce 앱은 앱이 4.0을 대상으로 하더라도 .NET Framework 4.5 이상이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="a06d0-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="a06d0-104">이제 .NET Framework 4.0을 대상으로 하는 ClickOnce 앱을 SHA-256으로 서명한 경우에도 .NET Framework 4.0에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a06d0-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="a06d0-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a06d0-105">Suggestion</span></span>|<span data-ttu-id="a06d0-106">이 변경 내용은 해당 종속성을 제거하고 .NET Framework 4 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06d0-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="a06d0-107">범위</span><span class="sxs-lookup"><span data-stu-id="a06d0-107">Scope</span></span>|<span data-ttu-id="a06d0-108">부</span><span class="sxs-lookup"><span data-stu-id="a06d0-108">Minor</span></span>|
|<span data-ttu-id="a06d0-109">버전</span><span class="sxs-lookup"><span data-stu-id="a06d0-109">Version</span></span>|<span data-ttu-id="a06d0-110">4.6</span><span class="sxs-lookup"><span data-stu-id="a06d0-110">4.6</span></span>|
|<span data-ttu-id="a06d0-111">형식</span><span class="sxs-lookup"><span data-stu-id="a06d0-111">Type</span></span>|<span data-ttu-id="a06d0-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="a06d0-112">Retargeting</span></span>|
