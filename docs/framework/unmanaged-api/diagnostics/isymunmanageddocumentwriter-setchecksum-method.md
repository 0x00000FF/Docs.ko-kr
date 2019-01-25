---
title: ISymUnmanagedDocumentWriter::SetCheckSum 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7a3fcd34f8cab6fa3c2949a4ee3270189b3dc77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730037"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="fdaa8-102">ISymUnmanagedDocumentWriter::SetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="fdaa8-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="fdaa8-103">체크섬 정보를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fdaa8-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdaa8-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdaa8-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdaa8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fdaa8-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="fdaa8-106">[in] 알고리즘 식별자를 나타내는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="fdaa8-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="fdaa8-107">[in] A `ULONG32` 의 크기 (바이트) 나타내는 `checkSum` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fdaa8-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="fdaa8-108">[in] 체크섬 정보를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fdaa8-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdaa8-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="fdaa8-109">Return Value</span></span>  
 <span data-ttu-id="fdaa8-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fdaa8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdaa8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdaa8-111">Requirements</span></span>  
 <span data-ttu-id="fdaa8-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fdaa8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdaa8-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="fdaa8-113">See also</span></span>
- [<span data-ttu-id="fdaa8-114">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdaa8-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
