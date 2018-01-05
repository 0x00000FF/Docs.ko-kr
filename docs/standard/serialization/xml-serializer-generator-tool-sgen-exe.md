---
title: "XML Serializer 생성기 도구(Sgen.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 005e78c32d49c8c1b204a3ac9376d943311868fd
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="xml-serializer-generator-tool-sgenexe"></a>XML Serializer 생성기 도구(Sgen.exe)
XML Serializer 생성기에서 지정된 어셈블리의 형식에 대해 XML serialization 어셈블리를 만들면 지정된 형식의 개체를 serialize 또는 deserialize할 때 <xref:System.Xml.Serialization.XmlSerializer>의 시작 성능을 높일 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
sgen [options]  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|옵션|설명|  
|------------|-----------------|  
|**/a**[**ssembly**]**:***filename*|*filename*에서 지정한 어셈블리 또는 실행 파일에 있는 모든 형식에 대해 serialization 코드를 생성합니다. 파일 이름은 하나만 제공할 수 있습니다. 이 인수가 반복되면 마지막 파일 이름이 사용됩니다.|  
|**/c[ompiler]:** *options*|C# 컴파일러로 전달될 옵션을 지정합니다. 모든 csc.exe 옵션이 컴파일러로 전달되어 지원됩니다. 이 옵션은 어셈블리에서 서명되도록 지정할 때와 키 파일을 지정할 때 사용할 수 있습니다.|  
|**/d**[**ebug**]|디버거에서 사용할 수 있는 이미지를 생성합니다.|  
|**/f[orce]**|이름이 같은 기존 어셈블리를 덮어쓰게 합니다. 기본값은 **false**입니다.|  
|**/help 또는 /?**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|**/k**[**eep**]|생성된 소스 파일 및 기타 임시 파일이 serialization 어셈블리로 컴파일된 후에는 이 파일을 삭제하지 않습니다. 이 도구에서 특정 형식에 대해 serialization 코드를 생성하는지 여부를 확인하는 데 사용할 수 있습니다.|  
|**/n**[**ologo**]|Microsoft 시작 배너를 표시하지 않습니다.|  
|**/o**[**ut**]**:***path*|생성된 어셈블리를 저장할 디렉터리를 지정합니다. **참고:** 생성된 어셈블리의 이름은 입력 어셈블리의 이름과 “xmlSerializers.dll”로 구성됩니다.|  
|**/p**[**roxytypes**]|XML Web services 프록시 형식에 대해서만 serialization 코드를 생성합니다.|  
|**/r**[**eference**]**:***assemblyfiles*|XML serialization이 필요한 형식에서 참조하는 어셈블리를 지정합니다. 여러 개의 어셈블리 파일을 쉼표로 구분할 수 있도록 허용합니다.|  
|**/s**[**ilent**]|성공 메시지를 표시하지 않습니다.|  
|**/t**[**ype**]**:***type*|지정된 형식에 대해서만 serialization 코드를 생성합니다.|  
|**/v**[**erbose**]|디버깅에 대한 자세한 출력을 표시합니다. 대상 어셈블리에서 <xref:System.Xml.Serialization.XmlSerializer>로 serialize할 수 없는 형식을 나열합니다.|  
|**/?**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
  
## <a name="remarks"></a>설명  
 XML Serializer 생성기를 사용하지 않을 경우, <xref:System.Xml.Serialization.XmlSerializer>는 응용 프로그램이 실행될 때마다 각 형식에 대해 serialization 코드 및 serialization 어셈블리를 생성합니다. XML serialization 시작 성능을 높이려면 Sgen.exe 도구를 사용하여 미리 어셈블리를 생성합니다. 그런 다음 응용 프로그램과 함께 이 어셈블리를 배포할 수 있습니다.  
  
 XML Serializer 생성기는 해당 형식이 맨 처음 로드될 때 serialization 프로세스에서 성능 손실을 유발하지 않으므로, 서버와의 통신에서 XML Web services 프록시를 사용하는 클라이언트의 성능도 높일 수 있습니다.  
  
 이렇게 생성된 어셈블리는 웹 서비스의 서버측에서는 사용할 수 없습니다. 이 도구는 웹 서비스 클라이언트 및 수동 serialization 시나리오에서만 사용할 수 있습니다.  
  
 serialize할 형식을 포함하는 어셈블리의 이름이 MyType.dll이라면 연결된 serialization 어셈블리의 이름은 MyType.XmlSerializers.dll이 됩니다.  
  
## <a name="examples"></a>예제  
 다음 명령에서는 Data.dll이라는 어셈블리에 포함된 모든 형식을 serialize하기 위해 Data.XmlSerializers.dll이라는 어셈블리를 만듭니다.  
  
```  
sgen Data.dll   
```  
  
 Data.XmlSerializers.dll 어셈블리는 Data.dll의 형식을 serialize/deserialize해야 하는 코드에서 참조할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [도구](../../../docs/framework/tools/index.md)  
 [XML 웹 서비스 개요](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)  
 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
