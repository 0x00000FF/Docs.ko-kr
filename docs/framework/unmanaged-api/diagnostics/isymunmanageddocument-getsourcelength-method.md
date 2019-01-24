---
title: ISymUnmanagedDocument::GetSourceLength 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: edafb60e5b6f9b913e89f4785dc34a58bf390f2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638771"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="d46e0-102">ISymUnmanagedDocument::GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="d46e0-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="d46e0-103">포함 소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d46e0-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d46e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="d46e0-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d46e0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d46e0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d46e0-106">[out] 포함 소스의 길이 (바이트)를 지정 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d46e0-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d46e0-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d46e0-107">Return Value</span></span>  
 <span data-ttu-id="d46e0-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="d46e0-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46e0-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="d46e0-109">See also</span></span>
- [<span data-ttu-id="d46e0-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d46e0-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
