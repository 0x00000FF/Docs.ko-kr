---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: da089e5342e641ffebe22ca6a4a593f97faeb89c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
현재 열거자와 동일한 상태인 다른 원시 입력 장치 열거자를 만들어 동일한 목록을 반복합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppenum`  
  
 [out] 수신 하는 출력 변수의 주소는 [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) 인터페이스 포인터입니다. 메서드가 실패할 경우이 출력 변수의 값을 정의 되지 않습니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT:이 메서드는 표준 반환 값 E_INVALIDARG 및 E_OUTOFMEMORY와 E_UNEXPECTED를 지원합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하면 나중에 해당 지점에 반환 하기 위해 한 지점을 열거 시퀀스에서 기록 하 합니다. 호출자에 게 첫 번째 열거자와는 별도로이 새로운 열거자를 해제 해야 합니다.
