---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: b03d141f1d2bfc18428c2f8651a340b789cfb995
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548557"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="3e4c4-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="3e4c4-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="3e4c4-103">열거자를 다음 건너뛰려면 지시 `celt` 열거형의 요소를 다음에 호출할 수 있도록 [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) 이러한 요소를 반환 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e4c4-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e4c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e4c4-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e4c4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e4c4-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="3e4c4-106">[in] 건너뛸 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3e4c4-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3e4c4-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="3e4c4-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="3e4c4-108">HRESULT: 제공된 요소 수가 `celt`이면 S_OK이고, 그러지 않으면 S_FALSE입니다.</span><span class="sxs-lookup"><span data-stu-id="3e4c4-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
