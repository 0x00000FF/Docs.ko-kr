---
title: 어셈블리 바인딩 리디렉션 보안 권한
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b9b9ac5c4e8ce08b9f926b0cdf7149dbdd9ac2da
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388968"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="6ac62-102">어셈블리 바인딩 리디렉션 보안 권한</span><span class="sxs-lookup"><span data-stu-id="6ac62-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="6ac62-103">응용 프로그램 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="6ac62-104">이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="6ac62-105">설정 하 여 사용 권한을 부여 합니다 <xref:System.Security.Permissions.SecurityPermissionFlag> 플래그를 <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="6ac62-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="6ac62-106">관리 되는 어셈블리 기본적으로 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="6ac62-107">보안 권한은 신뢰할 수 있는 영역 (로컬 컴퓨터) 및 인트라넷 영역에서 실행 중인 응용 프로그램에 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="6ac62-108">인터넷 영역에서 실행 중인 응용 프로그램 어셈블리 바인딩 리디렉션을 수행할 수 없도록 금지 엄격 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="6ac62-109">관리자가 제어 되는 컴퓨터 구성 파일 또는 구성 요소 게시자에 의해 제어 되는 게시자 정책 파일에 어셈블리 리디렉션을 수행 하는 경우에 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="6ac62-110">그러나 권한이 명시적으로 사용 하 여 게시자 정책 무시 하려면 응용 프로그램에 대 한 필요는 합니다 [ \<apply = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 응용 프로그램 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="6ac62-111">다음 표에서 기본 보안 설정 합니다 **BindingRedirects** 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="6ac62-112">영역</span><span class="sxs-lookup"><span data-stu-id="6ac62-112">Zone</span></span>|<span data-ttu-id="6ac62-113">BindingRedirects 플래그 설정</span><span class="sxs-lookup"><span data-stu-id="6ac62-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="6ac62-114">신뢰할 수 있는 영역 (로컬 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="6ac62-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="6ac62-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="6ac62-115">**ON**</span></span>|  
|<span data-ttu-id="6ac62-116">인트라넷 영역</span><span class="sxs-lookup"><span data-stu-id="6ac62-116">Intranet Zone</span></span>|<span data-ttu-id="6ac62-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="6ac62-117">**ON**</span></span>|  
|<span data-ttu-id="6ac62-118">인터넷 영역</span><span class="sxs-lookup"><span data-stu-id="6ac62-118">Internet Zone</span></span>|<span data-ttu-id="6ac62-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="6ac62-119">**OFF**</span></span>|  
|<span data-ttu-id="6ac62-120">신뢰할 수 없는 영역</span><span class="sxs-lookup"><span data-stu-id="6ac62-120">Untrusted zones</span></span>|<span data-ttu-id="6ac62-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="6ac62-121">**OFF**</span></span>|  
  
 <span data-ttu-id="6ac62-122">관리자 지원 하거나 지정된 된 컴퓨터에서 특정 시나리오를 제한 하려면 이러한 보안 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac62-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="6ac62-123">변경 하기 위한 도구가 합니다 **BindingRedirects** 기본값과; 설정 플래그 관리자로 수동으로 편집 해야 사용자의 컴퓨터 Security.config 파일.</span><span class="sxs-lookup"><span data-stu-id="6ac62-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac62-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ac62-124">See Also</span></span>  
 [<span data-ttu-id="6ac62-125">게시자 정책 파일 및 Side-by-side-실행</span><span class="sxs-lookup"><span data-stu-id="6ac62-125">Publisher Policy Files and Side-by-Side Execution</span></span>](https://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="6ac62-126">방법: 자동 바인딩 리디렉션 사용 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="6ac62-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="6ac62-127">Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="6ac62-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
