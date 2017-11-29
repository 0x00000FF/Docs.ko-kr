---
title: "ISymUnmanagedWriter3::OpenMethod2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3.OpenMethod2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1124eac951e32dbf1cedb7926f582ec6abb99007
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="6e22d-102">ISymUnmanagedWriter3::OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="6e22d-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="6e22d-103">메서드를 열고 하 고 이미지에 해당 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e22d-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e22d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e22d-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e22d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e22d-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="6e22d-106">[in] 열릴 메서드의 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e22d-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="6e22d-107">[in] 이미지에서 섹션 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6e22d-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="6e22d-108">[in] 이미지의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6e22d-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e22d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="6e22d-109">Return Value</span></span>  
 <span data-ttu-id="6e22d-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6e22d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e22d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e22d-111">Requirements</span></span>  
 <span data-ttu-id="6e22d-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6e22d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e22d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e22d-113">See Also</span></span>  
 [<span data-ttu-id="6e22d-114">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e22d-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 [<span data-ttu-id="6e22d-115">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="6e22d-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
