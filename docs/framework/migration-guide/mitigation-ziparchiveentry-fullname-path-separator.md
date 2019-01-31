---
title: '완화: ZipArchiveEntry.FullName 경로 구분 기호'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81da6f785394312dea92fffdbb00ce9d13f1bd6c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555650"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="87f3e-102">완화: ZipArchiveEntry.FullName 경로 구분 기호</span><span class="sxs-lookup"><span data-stu-id="87f3e-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="87f3e-103">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱부터 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> 속성에 사용되는 경로 구분 기호가 이전 버전의 .NET Framework에서 사용된 백슬래시("\\")에서 슬래시("/")로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="87f3e-104"><xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> 메서드의 오버로드 중 하나를 호출하여 <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="87f3e-105">영향</span><span class="sxs-lookup"><span data-stu-id="87f3e-105">Impact</span></span>  
 <span data-ttu-id="87f3e-106">이 변경으로 인해 .NET 구현은 [.ZIP 파일 형식 사양](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)의 섹션 4.4.17.1과 일치하게 되고 비 Windows 시스템에서.ZIP 아카이브의 압축이 풀리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="87f3e-107">Macintosh와 같은 비 Windows 운영 체제에서 이전 버전의 .NET Framework를 대상으로 하는 앱이 생성한 zip 파일의 압축을 풀면 디렉터리 구조가 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="87f3e-108">예를 들어 Macintosh에서는 해당 파일 이름이 디렉터리 경로, 백슬래시("\\") 문자 및 파일 이름으로 연결된 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="87f3e-109">결과적으로 압축을 푼 파일의 디렉터리 구조는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="87f3e-110">.NET Framework <xref:System.IO> 네임스페이스의 API는 슬래시("/") 또는 백슬래시("\\")를 경로 구분 기호 문자로 원활하게 처리할 수 있으므로 이러한 API에 의해 Windows 운영 체제에서 압축 해제된 .ZIP 파일에 이러한 변경이 미치는 영향은 최소로 유지될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="87f3e-111">완화</span><span class="sxs-lookup"><span data-stu-id="87f3e-111">Mitigation</span></span>  
 <span data-ttu-id="87f3e-112">이 동작을 원치 않을 경우 애플리케이션 구성 파일의 [\<runtime&gt;](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="87f3e-113">다음에서는 `<runtime>` 섹션 및 옵트아웃 스위치를 둘 다 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="87f3e-114">또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이후 버전에서 실행되는 앱은 애플리케이션 구성 파일의 [\<runtime&gt;](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-114">In addition, apps that target previous versions of the .NET Framework but are running on the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="87f3e-115">다음에서는 `<runtime>` 섹션 및 옵트인 스위치를 둘 다 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87f3e-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87f3e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87f3e-116">See also</span></span>
- [<span data-ttu-id="87f3e-117">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="87f3e-117">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
- [<span data-ttu-id="87f3e-118">4.6.1의 애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="87f3e-118">Application Compatibility in 4.6.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
