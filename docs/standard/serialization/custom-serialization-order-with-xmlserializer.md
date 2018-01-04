---
title: "XmlSerializer를 통한 사용자 지정 Serialization 순서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae5969060938763fee63c514de0a87eadbe6537a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="custom-serialization-order-with-xmlserializer"></a>XmlSerializer를 통한 사용자 지정 Serialization 순서
[샘플 다운로드](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 이 샘플에서는 XML serialization에서 serialize 및 deserialize되는 요소의 순서를 제어하는 방법을 보여 줍니다.  
  
 serialization에 대한 자세한 내용은 build.proj 파일 및 소스 코드의 주석을 참조하십시오.  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a>명령 프롬프트를 사용하여 샘플을 빌드하려면  
  
1.  명령 프롬프트 창을 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.  
  
2.  명령줄에 **msbuild CustomOrder.sln**을 입력합니다.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Visual Studio를 사용하여 샘플을 빌드하려면  
  
1.  [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.  
  
2.  CustomOrder.sln의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
4.  샘플 응용 프로그램이 기본 \bin 또는 \bin\Debug 하위 디렉터리에 빌드됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 serialization](../../../docs/standard/serialization/basic-serialization.md)  
 [이진 serialization](../../../docs/standard/serialization/binary-serialization.md)  
 [특성을 사용하여 XML serialization 제어](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [XML serialization 소개](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [serialization](../../../docs/standard/serialization/index.md)  
 [XML 및 SOAP serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)
