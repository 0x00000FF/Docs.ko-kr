---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 4a3e45140765f99f4a30b77fc9d02b167601b50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591482"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="9e5c3-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9e5c3-102">ChannelPoolSettings</span></span>
<span data-ttu-id="9e5c3-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9e5c3-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e5c3-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9e5c3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9e5c3-105">Methods</span></span>  
 <span data-ttu-id="9e5c3-106">ChannelPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5c3-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9e5c3-107">속성</span><span class="sxs-lookup"><span data-stu-id="9e5c3-107">Properties</span></span>  
 <span data-ttu-id="9e5c3-108">ChannelPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5c3-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="9e5c3-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="9e5c3-109">IdleTimeout</span></span>  
 <span data-ttu-id="9e5c3-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="9e5c3-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="9e5c3-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9e5c3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e5c3-112">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5c3-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="9e5c3-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="9e5c3-113">LeaseTimeout</span></span>  
 <span data-ttu-id="9e5c3-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="9e5c3-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="9e5c3-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9e5c3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e5c3-116">시간 제한을 초과하기 전에 대여 작업을 완료하기 위한 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5c3-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="9e5c3-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9e5c3-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="9e5c3-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9e5c3-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="9e5c3-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9e5c3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e5c3-120">각 엔드포인트에 대한 최대 아웃바운드 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5c3-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e5c3-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e5c3-121">Requirements</span></span>  
  
|<span data-ttu-id="9e5c3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9e5c3-122">MOF</span></span>|<span data-ttu-id="9e5c3-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5c3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9e5c3-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9e5c3-124">Namespace</span></span>|<span data-ttu-id="9e5c3-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5c3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e5c3-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e5c3-126">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
