---
title: ICorDebugFunction2::EnumerateNativeCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959967"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="0ec9a-102">ICorDebugFunction2::EnumerateNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="0ec9a-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="0ec9a-103">이 ICorDebugFunction2 개체에서 참조 하는 함수에서 네이티브 코드 문을 포함 하는 ICorDebugCodeEnum 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec9a-104">`EnumerateNativeCode` 현재 버전의.NET Framework에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec9a-105">구문</span><span class="sxs-lookup"><span data-stu-id="0ec9a-105">Syntax</span></span>  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0ec9a-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ec9a-106">Requirements</span></span>  
 <span data-ttu-id="0ec9a-107">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ec9a-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
