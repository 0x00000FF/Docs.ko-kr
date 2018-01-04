---
title: "IMetaDataImport2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2
helpviewer_keywords: IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7cd9d2cd2837ff43fbb266717546db3aa98190e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="ccdf0-102">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccdf0-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="ccdf0-103">확장 된 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스의 제네릭 형식 작업 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ccdf0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-104">Methods</span></span>  
  
|<span data-ttu-id="ccdf0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-105">Method</span></span>|<span data-ttu-id="ccdf0-106">설명</span><span class="sxs-lookup"><span data-stu-id="ccdf0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ccdf0-107">EnumGenericParamConstraints 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="ccdf0-108">제네릭 매개 변수 제약 조건을 지정한 토큰이 나타내는 제네릭 매개 변수와 관련 된 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="ccdf0-109">EnumGenericParams 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="ccdf0-110">지정한 TypeDef 또는 MethodDef와 연결 된 제네릭 매개 변수 토큰의 배열을 토큰 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="ccdf0-111">EnumMethodSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="ccdf0-112">지정한 MethodDef 또는 MemberRef 연관 MethodSpec 토큰 배열의 토큰 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="ccdf0-113">GetGenericParamConstraintProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="ccdf0-114">지정 된 제약 조건 토큰이 나타내는 제네릭 매개 변수 제약 조건과 연관 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="ccdf0-115">GetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="ccdf0-116">지정한 토큰이 나타내는 제네릭 매개 변수와 연관 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="ccdf0-117">GetMethodSpecProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="ccdf0-118">토큰을 지정 된 MethodSpec 참조 메서드의 메타 데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="ccdf0-119">GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="ccdf0-120">가져옵니다 이식 가능한 실행 (PE)에서 코드의 특성을 식별 하는 값 파일을 일반적으로 DLL 또는 EXE 파일을 현재 메타 데이터 범위에 정의 된</span><span class="sxs-lookup"><span data-stu-id="ccdf0-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="ccdf0-121">GetVersionString 메서드</span><span class="sxs-lookup"><span data-stu-id="ccdf0-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="ccdf0-122">어셈블리를 빌드하는 데 사용 된 런타임 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccdf0-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccdf0-123">Requirements</span></span>  
 <span data-ttu-id="ccdf0-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ccdf0-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccdf0-125">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ccdf0-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccdf0-126">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ccdf0-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccdf0-127">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccdf0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccdf0-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccdf0-128">See Also</span></span>  
 <xref:System.Reflection.PortableExecutableKinds>  
 [<span data-ttu-id="ccdf0-129">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccdf0-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="ccdf0-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccdf0-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
