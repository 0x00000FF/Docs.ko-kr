---
title: ForwardTranslateAccelerator 함수 (WPF 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: d8a296c0590d07c4929610021714d2a257236d67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542563"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="46037-102">ForwardTranslateAccelerator 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="46037-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="46037-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46037-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="46037-104">Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46037-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46037-105">구문</span><span class="sxs-lookup"><span data-stu-id="46037-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46037-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46037-106">Parameters</span></span>  
 <span data-ttu-id="46037-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="46037-107">pMsg</span></span>  
 <span data-ttu-id="46037-108">메시지에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46037-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="46037-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="46037-109">appUnhandled</span></span>  
 <span data-ttu-id="46037-110">`true` 응용 프로그램 입력된 메시지를 처리할 수 있는 기회가 부여 이미 하지만, 처리 되지 않은 경우 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="46037-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46037-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46037-111">Requirements</span></span>  
 <span data-ttu-id="46037-112">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46037-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46037-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="46037-113">**DLL:**</span></span>  
  
 <span data-ttu-id="46037-114">.NET framework 3.0 및 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="46037-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="46037-115">.NET Framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="46037-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="46037-116">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46037-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46037-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46037-117">See Also</span></span>  
 [<span data-ttu-id="46037-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="46037-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
