---
title: "ISymUnmanagedReaderSymbolSearchInfo 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReaderSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords: ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7f53e45eb321f114483648afc63d2669065a791
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="129eb-102">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="129eb-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="129eb-103">기호 검색 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="129eb-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="129eb-104">이 인터페이스를 호출 하 여 가져올 `QueryInterface` 구현 하는 개체에는 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="129eb-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="129eb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="129eb-105">Methods</span></span>  
  
|<span data-ttu-id="129eb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="129eb-106">Method</span></span>|<span data-ttu-id="129eb-107">설명</span><span class="sxs-lookup"><span data-stu-id="129eb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="129eb-108">GetSymbolSearchInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="129eb-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="129eb-109">기호 검색 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="129eb-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="129eb-110">GetSymbolSearchInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="129eb-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="129eb-111">기호 검색 정보의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="129eb-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="129eb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="129eb-112">Requirements</span></span>  
 <span data-ttu-id="129eb-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="129eb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="129eb-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="129eb-114">See Also</span></span>  
 [<span data-ttu-id="129eb-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="129eb-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
