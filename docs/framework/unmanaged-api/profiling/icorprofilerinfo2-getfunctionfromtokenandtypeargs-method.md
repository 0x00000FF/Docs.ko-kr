---
title: "ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b225b87eab6e65055618c8b6659459637e8a01be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드
가져옵니다는 `FunctionID` 클래스가 포함 된 지정 된 메타 데이터 토큰을 사용 하 여 함수의 및 `ClassID` 값 형식 인수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] 함수가 상주 하는 모듈의 ID입니다.  
  
 `funcDef`  
 [in] `mdMethodDef` 함수를 참조 하는 메타 데이터 토큰입니다.  
  
 `classId`  
 [in] 함수의 포함 하는 클래스의 ID입니다.  
  
 `cTypeArgs`  
 [in] 지정된 된 함수에 대 한 형식 매개 변수 수를 지정 합니다. 이 값에는 제네릭이 아닌 함수에 대 한 0 이어야 합니다.  
  
 `typeArgs`  
 [in] 배열 `ClassID` 된 함수의 인수 값입니다. 값 `typeArgs` 경우 NULL이 될 수 `cTypeArgs` 0으로 설정 됩니다.  
  
 `pFunctionID`  
 [out] 에 대 한 포인터는 `FunctionID` 지정 된 함수입니다.  
  
## <a name="remarks"></a>설명  
 호출의 `GetFunctionFromTokenAndTypeArgs` 메서드는 `mdMethodRef` 대신 메타 데이터는 `mdMethodDef` 메타 데이터 토큰에서 예기치 않은 결과 가질 수 있습니다. 호출자에 게 해결 해야는 `mdMethodRef` 에 `mdMethodDef` 전달할 경우.  
  
 함수가 아직 로드 되지 않은 경우 호출 `GetFunctionFromTokenAndTypeArgs` 여러 컨텍스트에서 위험한 작업 발생을 로드 하면 합니다. 예를 들어, 런타임에서 순환 로드를 시도할 때 모듈이 나 형식을 로드 하는 동안이 메서드를 호출 무한 루프가 발생할 수입니다.  
  
 일반적으로 사용 하 여 `GetFunctionFromTokenAndTypeArgs` 않는 것이 좋습니다. 저장 해야 프로파일러 특정 기능에 대 한 이벤트에 관심이 `ModuleID` 및 `mdMethodDef` 해당 기능에 [icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 확인 하려면 여부는 주어진 `FunctionID` 은 원하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
