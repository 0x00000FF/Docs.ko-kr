---
title: AssemblyOptions 열거형
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085417"
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions 열거형
어셈블리 옵션을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>필드  
  
|필드|설명|  
|-----------|-----------------|  
|optAssemTitle|문자열-어셈블리 제목을 나타냅니다.|  
|optAssemDescription|문자열-어셈블리 파일에 대 한 설명을 포함 합니다.|  
|optAssemConfig|문자열-어셈블리 구성을 포함 합니다.|  
|optAssemOS|로 인코드된 문자열: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"입니다.|  
|optAssemProcessor|ULONG|  
|optAssemLocale|문자열-어셈블리 로캘을 포함 합니다.|  
|optAssemVersion|문자열-로 인코딩됩니다. "Major.Minor.Build.Revision".|  
|optAssemCompany|문자열-회사 이름을 포함 합니다.|  
|optAssemProduct|문자열-제품 이름을 포함 합니다.|  
|optAssemProductVersion|문자열 (InformationalVersion이 라고도 함)입니다.|  
|optAssemCopyright|문자열-저작권 정보를 포함 합니다.|  
|optAssemTrademark|문자열-상표 정보를 포함 합니다.|  
|optAssemKeyFile|String (파일 이름)입니다.|  
|optAssemKeyName|문자열 (키 이름)입니다.|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (DelaySign 라고도 함)입니다.|  
|optAssemFileVersion|String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.|  
|optAssemSatelliteVer|문자열-"Major.Minor.Build.Revision"로 인코딩됩니다.|  
|optLastAssemOption|요소 수가 카운터입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** alink.h  
  
 **라이브러리**: alink.dll  
  
## <a name="see-also"></a>참고자료

- [Al.exe(어셈블리 링커)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
