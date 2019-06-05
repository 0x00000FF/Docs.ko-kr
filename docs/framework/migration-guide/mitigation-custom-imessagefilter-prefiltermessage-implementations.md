---
title: '완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3ac43b574c4382c4aec5070acde0fa77516727d
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251141"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="e93ab-102">완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현</span><span class="sxs-lookup"><span data-stu-id="e93ab-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="e93ab-103">.NET Framework 4.6.1부터 .NET Framework 버전을 대상으로 하는 Windows Forms 앱에서는 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 다음에 해당하는 경우 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드를 호출할 때 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 메시지를 안전하게 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93ab-103">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="e93ab-104">다음 중 하나 또는 두 가지 모두를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e93ab-104">Does one or both of the following:</span></span>

  - <span data-ttu-id="e93ab-105"><xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드를 호출하여 메시지 필터 추가</span><span class="sxs-lookup"><span data-stu-id="e93ab-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="e93ab-106"><xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 메서드를 호출하여 메시지 필터 제거</span><span class="sxs-lookup"><span data-stu-id="e93ab-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="e93ab-107">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e93ab-107">method.</span></span>

- <span data-ttu-id="e93ab-108">**그와 동시에** <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 메서드를 호출하여 메시지를 펌핑하는 경우</span><span class="sxs-lookup"><span data-stu-id="e93ab-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="e93ab-109">영향</span><span class="sxs-lookup"><span data-stu-id="e93ab-109">Impact</span></span>

<span data-ttu-id="e93ab-110">이 변경은 .NET Framework 4.6.1부터 .NET Framework 버전을 대상으로 하는 Windows Forms 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e93ab-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="e93ab-111">이전 버전의 .NET Framework를 대상으로 하는 Windows Forms 앱에서는 경우에 따라 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드를 호출할 때 이러한 구현이 <xref:System.IndexOutOfRangeException> 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93ab-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="e93ab-112">완화</span><span class="sxs-lookup"><span data-stu-id="e93ab-112">Mitigation</span></span>

<span data-ttu-id="e93ab-113">이러한 변경을 원치 않는 경우 .NET Framework 4.6.1 이상 버전을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93ab-113">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="e93ab-114">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.1 이상 버전에서 실행되는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93ab-114">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="e93ab-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e93ab-115">See also</span></span>

- [<span data-ttu-id="e93ab-116">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="e93ab-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
