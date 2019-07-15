---
ms.openlocfilehash: a26b8c8a6315e57e70f4810ac4f5fb7ab4ba9b58
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857220"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="35f1b-101">addressHeader 요소가 null인 경우 이제 WCF AddressHeaderCollection이 ArgumentException을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="35f1b-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

|   |   |
|---|---|
|<span data-ttu-id="35f1b-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="35f1b-102">Details</span></span>|<span data-ttu-id="35f1b-103">.NET Framework 4.7.1부터 요소 중 하나가 <code>null</code>이면 <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> 생성자가 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="35f1b-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="35f1b-104">.NET Framework 4.7 및 이전 버전에서 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35f1b-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>|
|<span data-ttu-id="35f1b-105">제안</span><span class="sxs-lookup"><span data-stu-id="35f1b-105">Suggestion</span></span>|<span data-ttu-id="35f1b-106">.NET Framework 4.7.1 또는 이후 버전에서 이러한 변경으로 인해 호환성 문제가 발생하는 경우 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 줄을 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f1b-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="35f1b-107">범위</span><span class="sxs-lookup"><span data-stu-id="35f1b-107">Scope</span></span>|<span data-ttu-id="35f1b-108">부</span><span class="sxs-lookup"><span data-stu-id="35f1b-108">Minor</span></span>|
|<span data-ttu-id="35f1b-109">버전</span><span class="sxs-lookup"><span data-stu-id="35f1b-109">Version</span></span>|<span data-ttu-id="35f1b-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="35f1b-110">4.7.1</span></span>|
|<span data-ttu-id="35f1b-111">형식</span><span class="sxs-lookup"><span data-stu-id="35f1b-111">Type</span></span>|<span data-ttu-id="35f1b-112">런타임</span><span class="sxs-lookup"><span data-stu-id="35f1b-112">Runtime</span></span>|
|<span data-ttu-id="35f1b-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="35f1b-113">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})?displayProperty=nameWithType></li></ul>|

