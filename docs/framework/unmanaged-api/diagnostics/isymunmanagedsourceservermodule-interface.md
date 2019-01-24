---
title: ISymUnmanagedSourceServerModule 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4fed0fcd806bd410c8a6817447e6fd634237624d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743181"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="12073-102">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12073-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="12073-103">모듈에 대 한 원본 서버 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="12073-103">Provides source server data for a module.</span></span> <span data-ttu-id="12073-104">호출 하 여이 인터페이스를 가져올 `QueryInterface` 구현 하는 개체에는 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="12073-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12073-105">메서드</span><span class="sxs-lookup"><span data-stu-id="12073-105">Methods</span></span>  
  
|<span data-ttu-id="12073-106">메서드</span><span class="sxs-lookup"><span data-stu-id="12073-106">Method</span></span>|<span data-ttu-id="12073-107">설명</span><span class="sxs-lookup"><span data-stu-id="12073-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12073-108">GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="12073-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="12073-109">모듈에 대 한 원본 서버 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="12073-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12073-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12073-110">Requirements</span></span>  
 <span data-ttu-id="12073-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12073-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12073-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="12073-112">See also</span></span>
- [<span data-ttu-id="12073-113">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12073-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
