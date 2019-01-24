---
title: IDebugAutoAttach::AutoAttach 메서드
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b45b5e1a7589329b788160df3ac4493efa48197
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663520"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="456c2-102">IDebugAutoAttach::AutoAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="456c2-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="456c2-103">서버에서 호출한 디버거 자동 수행 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="456c2-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="456c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="456c2-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="456c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="456c2-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="456c2-106">[in] 항상로 `GUID_NULL`합니다.</span><span class="sxs-lookup"><span data-stu-id="456c2-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="456c2-107">[in] 프로세스 ID, 일반적으로 사용 하 여 검색 된 `GetCurrentProcessId` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="456c2-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="456c2-108">[in] 프로그램 형식: `AUTOATTACH_PROGRAM_WIN32`하십시오 `AUTOATTACH_PROGRAM_COMPLUS`, 또는 `AUTOATTACH_PROGRAM_UNKNOWN`합니다.</span><span class="sxs-lookup"><span data-stu-id="456c2-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="456c2-109">[in] 프로그램 id입니다.</span><span class="sxs-lookup"><span data-stu-id="456c2-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="456c2-110">[in] Debug 동사를 전달한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="456c2-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="456c2-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="456c2-111">Return Value</span></span>  
 <span data-ttu-id="456c2-112">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="456c2-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="456c2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="456c2-113">Requirements</span></span>  
 <span data-ttu-id="456c2-114">**헤더:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="456c2-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456c2-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="456c2-115">See also</span></span>
- [<span data-ttu-id="456c2-116">IDebugAutoAttach 인터페이스</span><span class="sxs-lookup"><span data-stu-id="456c2-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
