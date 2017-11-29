---
title: "ICorDebugThread2::GetConnectionID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetConnectionID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae852fe91bdb15007437ea6f2c61cbaa49a6918b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="feac8-102">ICorDebugThread2::GetConnectionID 메서드</span><span class="sxs-lookup"><span data-stu-id="feac8-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="feac8-103">이 ICorDebugThread2 개체에 대 한 연결 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="feac8-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feac8-104">구문</span><span class="sxs-lookup"><span data-stu-id="feac8-104">Syntax</span></span>  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="feac8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="feac8-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="feac8-106">[out] A `CONNID` 연결 식별자를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="feac8-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feac8-107">설명</span><span class="sxs-lookup"><span data-stu-id="feac8-107">Remarks</span></span>  
 <span data-ttu-id="feac8-108">`GetConnectionID` 변수에 0을 반환 하는 메서드는 `pdwConnectionId` 매개 변수를이 스레드는 연결의 일부가 아닌 경우.</span><span class="sxs-lookup"><span data-stu-id="feac8-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="feac8-109">이 스레드가의 Microsoft SQL Server 2005 Analysis Services (SSAS), 인스턴스에 연결 되어 있는 경우는 `CONNID` 서버 프로세스 식별자 (SPID)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="feac8-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feac8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="feac8-110">Requirements</span></span>  
 <span data-ttu-id="feac8-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="feac8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feac8-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="feac8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="feac8-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feac8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feac8-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feac8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
