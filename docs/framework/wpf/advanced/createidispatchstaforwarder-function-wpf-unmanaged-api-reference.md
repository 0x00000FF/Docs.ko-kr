---
title: "CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: CreateIDispatchSTAForwarder
api_location: PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63195ce2a47add2606f528b18d0d1d58ab0d968c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="5941d-102">CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="5941d-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="5941d-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5941d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="5941d-104">스레드 및 창 관리를 위한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5941d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5941d-105">구문</span><span class="sxs-lookup"><span data-stu-id="5941d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5941d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5941d-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5941d-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="5941d-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="5941d-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="5941d-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="5941d-109">에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5941d-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="5941d-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="5941d-110">ppForwarder</span></span>  
 <span data-ttu-id="5941d-111">주소에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5941d-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5941d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5941d-112">Requirements</span></span>  
 <span data-ttu-id="5941d-113">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5941d-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5941d-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="5941d-114">**DLL:**</span></span>  
  
 <span data-ttu-id="5941d-115">.NET framework 3.0 및 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="5941d-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="5941d-116">.NET Framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="5941d-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="5941d-117">**.NET framework 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5941d-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5941d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5941d-118">See Also</span></span>  
 [<span data-ttu-id="5941d-119">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="5941d-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
