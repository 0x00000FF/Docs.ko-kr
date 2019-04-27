---
title: ICorProfilerCallback::MovedReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4611b8c186e0293dae73cee4f9d845bb44c167c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904711"
---
# <a name="icorprofilercallbackmovedreferences-method"></a>ICorProfilerCallback::MovedReferences 메서드
압축 가비지 수집의 결과로 힙에 있는 개체의 새 레이아웃을 보고하려고 호출됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>매개 변수  
 `cMovedObjectIDRanges`  
 [in] 압축 가비지 컬렉션 후에 이동된 연속 개체 블록 수입니다. 즉, `cMovedObjectIDRanges` 값은 `oldObjectIDRangeStart`, `newObjectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 총 크기입니다.  
  
 `MovedReferences`의 다음 세 인수는 병렬 배열입니다. 즉, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` 및 `cObjectIDRangeLength[i]`는 모두 단일 연속 개체 블록과 관련이 있습니다.  
  
 `oldObjectIDRangeStart`  
 [in] 메모리에서 연속 라이브 개체 블록의 이전(가비지 수집 전) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.  
  
 `newObjectIDRangeStart`  
 [in] 메모리에서 연속 라이브 개체 블록의 새(가비지 컬렉션 후) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.  
  
 `cObjectIDRangeLength`  
 [in] 메모리의 연속 개체 블록의 크기를 각각 나타내는 정수 배열입니다.  
  
 크기는 `oldObjectIDRangeStart` 및 `newObjectIDRangeStart` 배열에서 참조된 각 블록에 대해 지정됩니다.  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  이 메서드는 64비트 플랫폼에서 4GB보다 큰 개체의 크기를 `MAX_ULONG`으로 보고합니다. 4GB 보다 큰 개체의 크기를 사용 합니다 [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) 메서드 대신 합니다.  
  
 압축 가비지 수집기는 데드 개체가 사용한 메모리를 회수하고 확보된 공간을 압축합니다. 따라서 라이브 개체가 힙 내에서 이동될 수 있고 이전 알림으로 분산된 `ObjectID` 값이 변경될 수 있습니다.  
  
 기존 `ObjectID` 값(`oldObjectID`)이 다음 범위 내에 있다고 가정합니다.  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 이 경우 범위 시작부터 개체 시작까지 오프셋은 다음과 같습니다.  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 다음 범위에 있는 `i` 값에 대해  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 새 `ObjectID`를 다음과 같이 계산할 수 있습니다.  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)  
  
 콜백 자체가 진행되는 동안 `MovedReferences`를 통해 전달된 `ObjectID` 값은 유효하지 않습니다. 가비지 수집이 이전 위치에서 새 위치로 개체를 이동하는 중일 수 있기 때문입니다. 그러므로 프로파일러는 `MovedReferences` 호출 중에 개체 검사를 시도하지 않아야 합니다. A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 콜백 나타내고 모든 개체가 새 위치로 이동 된 검사를 수행할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [MovedReferences2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
