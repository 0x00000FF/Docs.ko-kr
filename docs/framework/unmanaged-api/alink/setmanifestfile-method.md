---
title: SetManifestFile 메서드
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8307960166cfc668a577431d688c439f0f794be2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949045"
---
# <a name="setmanifestfile-method"></a>SetManifestFile 메서드
지정 하거나 어셈블리를 만들 때 링커에서 사용 하는 매니페스트 파일을 다시 설정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `pszFile`  
  
 Win32 리소스 blob 콘텐츠가 저장 된 매니페스트 파일의 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 Win32ResBlob 요청 하기 전에이 호출 합니다. 값을 `pszFile` 매개 변수는 해당 내용을 읽고 RT_MANIFEST의 ID를 사용 하 여 Win32 리소스에 매니페스트 파일의 이름입니다. NULL의 매개 변수를 사용 하 여 호출 되 면 이전에 읽은 매니페스트가 지워집니다. 초기화 시에 링커의 상태를 다시 설정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 ALink.h 필요  
  
## <a name="see-also"></a>참고자료

- [IALink3 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Al.exe(어셈블리 링커)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
