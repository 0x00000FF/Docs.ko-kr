---
title: ISymUnmanagedDispose 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90f5924bc03a9896442fd61a4c618d18ed999faf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638875"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="8052f-102">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8052f-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="8052f-103">관리 되지 않는 리소스를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8052f-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8052f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8052f-104">Methods</span></span>  
  
|<span data-ttu-id="8052f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8052f-105">Method</span></span>|<span data-ttu-id="8052f-106">설명</span><span class="sxs-lookup"><span data-stu-id="8052f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8052f-107">Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="8052f-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="8052f-108">이 인해 기본 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8052f-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8052f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8052f-109">Requirements</span></span>  
 <span data-ttu-id="8052f-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8052f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8052f-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="8052f-111">See also</span></span>
- [<span data-ttu-id="8052f-112">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8052f-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
