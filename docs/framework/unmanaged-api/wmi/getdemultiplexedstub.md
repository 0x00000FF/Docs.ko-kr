---
title: GetDemultiplexedStub 함수 (관리 되지 않는 API 참조)
description: GetDemultiplexedStub 함수에는 Windows 관리에서 비동기 호출을 수신할 클라이언트를 지원 하기 위해 개체 전달자 싱크를 만듭니다.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4311a77c9159428bf7beacc99d4479acb28b91b6
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037216"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="cfabc-103">GetDemultiplexedStub 함수</span><span class="sxs-lookup"><span data-stu-id="cfabc-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="cfabc-104">클라이언트가 Windows 관리에서 비동기 호출을 수신하는 데 도움이 되는 개체 전달자 싱크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cfabc-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="cfabc-105">구문</span><span class="sxs-lookup"><span data-stu-id="cfabc-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="cfabc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfabc-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="cfabc-107">[in] 클라이언트의 in process 구현에 대 한 포인터 [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)합니다.</span><span class="sxs-lookup"><span data-stu-id="cfabc-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="cfabc-108">[in] 이벤트를 로컬 인지 여부를 나타내는 플래그입니다 (`true`)이 고, 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="cfabc-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="cfabc-109">[out] Windows 관리에서 비동기 호출을 수신할 클라이언트를 지원 하기 위해 개체 전달자 싱크.</span><span class="sxs-lookup"><span data-stu-id="cfabc-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="cfabc-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="cfabc-110">Return value</span></span>

<span data-ttu-id="cfabc-111">함수가 성공할 경우 반환 값은 `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="cfabc-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="cfabc-112">함수가 실패 한 경우 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cfabc-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="cfabc-113">오류 정보를 호출 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cfabc-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="cfabc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfabc-114">Requirements</span></span>  
 <span data-ttu-id="cfabc-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfabc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfabc-116">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cfabc-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="cfabc-117">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cfabc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfabc-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="cfabc-118">See also</span></span>  
[<span data-ttu-id="cfabc-119">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="cfabc-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
