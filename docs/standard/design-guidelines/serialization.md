---
title: Serialization1
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: KrzysztofCwalina
ms.openlocfilehash: 3e21251710a44764bd06fbce83f97288b6925bc2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155108"
---
# <a name="serialization"></a>Serialization
Serialization은 개체를 쉽게 유지 또는 전송할 수 있는 형식으로 변환 하는 프로세스입니다. 예를 들어 개체를 serialize 하, 대상 컴퓨터에서 역직렬화 HTTP를 사용 하 여 인터넷을 통해 전송할 수 있습니다.  
  
 .NET Framework는 다양 한 serialization 시나리오에 대 한 액세스에 최적화 된 세 가지 기본 serialization 기술을 제공 합니다. 다음 표에서는 이러한 기술 및 해당 기술과 관련된 기본 Framework 형식을 보여 줍니다.  
  
|**기술 이름**|**기본 형식**|**시나리오**|  
|-------------------------|--------------------|-------------------|  
|**데이터 계약 Serialization**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|일반 지속성<br />웹 서비스<br />JSON|  
|**XML Serialization**|<xref:System.Xml.Serialization.XmlSerializer>|XML의 모양 상세하게 전체 컨트롤을 사용 하 여 XML 형식|  
|**런타임 Serialization (이진 및 SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|  
  
 **✓ DO** serialization 새 형식을 디자인할 때 고려해 야 합니다.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>지원할 올바른 Serialization 기술 선택  
 **✓ CONSIDER** 데이터 계약 Serialization을 지 원하는 지속 또는 웹 서비스에서 사용 하 여의 인스턴스 해 보십시오.  
  
 **✓ CONSIDER** 형식이 serialize 될 때 생성 되는 XML 형식 보다 자세히 제어 해야 하는 경우 대신 또는 데이터 계약 Serialization 함께 XML Serialization을 지원 합니다.  
  
 이 일부 상호 운용성에 XML을 사용 해야 하는 시나리오 생성 지원 되지 않는 데이터 계약 Serialization에서 예를 들어, XML 특성을 생성 하기 위해 필요할 수 있습니다.  
  
 **✓ CONSIDER** .NET Remoting 경계를 넘어 이동 하 여의 인스턴스 필요 런타임 Serialization을 지원 합니다.  
  
 **X AVOID** 이유로 일반 지 속성에 대 한 런타임 Serialization 또는 XML 직렬화를 지원 합니다. 대신 데이터 계약 Serialization을 선호 합니다.  
  
## <a name="supporting-data-contract-serialization"></a>데이터 계약 Serialization 지원  
 형식을 적용 하 여 데이터 계약 Serialization을 지원할 수는 <xref:System.Runtime.Serialization.DataContractAttribute> 형식 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 형식의 멤버 (필드 및 속성).  
  
 **✓ CONSIDER** 형식을 부분 신뢰 환경에서 사용할 수 있는 경우 형식 공용 데이터 멤버를 표시 합니다.  
  
 완전 신뢰를 데이터 계약 serializer가 serialize 및 public이 아닌 형식과 멤버를 deserialize 할 수 있지만 공용 멤버만 직렬화 하 고 부분 신뢰에서 deserialize 할 수 있습니다.  
  
 **✓ DO** 되어 있는 모든 속성에 getter와 setter 구현 <xref:System.Runtime.Serialization.DataMemberAttribute>합니다. 데이터 계약 serializer에 getter와 setter serializable 간주 되기 위해 형식에 대 한 필요 합니다. .NET Framework 3.5 SP1의 몇 가지 컬렉션 속성 일 수 있습니다 가져오기 전용입니다. 부분 신뢰에서 사용하지 않을 형식의 경우에는 두 속성 접근자 중 하나 또는 둘 다 public이 아닐 수 있습니다.  
  
 **✓ CONSIDER** 역직렬화 된 인스턴스의 초기화에 대 한 serialization 콜백을 사용 하 여 합니다.  
  
 개체가 deserialize될 때는 생성자가 호출되지 않습니다. (규칙의 예외는 있습니다. 생성자 컬렉션으로 표시 된 <xref:System.Runtime.Serialization.CollectionDataContractAttribute> 역직렬화 하는 동안 호출 됩니다.) 따라서 정상적인 생성 하는 동안 실행 하는 모든 논리가 serialization 콜백 중 하나로 구현 해야 합니다.  
  
 `OnDeserializedAttribute` 가장 일반적으로 사용 되는 콜백 특성이입니다. 패밀리의 다른 특성으로는 <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> 및 <xref:System.Runtime.Serialization.OnSerializedAttribute>가 있습니다. 이 특성은 deserialization하기 전, serialization하기 전 및 마지막으로 serialization한 후에 각각 실행되는 콜백을 표시하는 데 사용할 수 있습니다.  
  
 **✓ CONSIDER** 를 사용 하 여는 <xref:System.Runtime.Serialization.KnownTypeAttribute> 복잡 한 개체 그래프를 역직렬화 할 때 사용 해야 하는 구체적인 형식을 나타냅니다.  
  
 **✓ DO** 를 만들거나 직렬화 형식을 변경할 때 뒤로 및 앞으로 호환성을 고려해 야 합니다.  
  
 이후 버전의 형식에 대한 serialize된 스트림을 현재 버전의 형식으로 deserialize할 수 있고, 그 반대로 deserialize할 수도 있습니다.  
  
 데이터 계약 특성을 명시적 매개 변수를 사용 하는 계약을 유지 하기 위해 특별히 주의 하지 않으면 해당 이름, 형식 또는 형식의 이후 버전에서의 순서에도 데이터 멤버에도 개인 및 내부를 변경할 수 없습니다를 알고 있는지 확인 .  
  
 직렬화 가능 형식으로 변경 하는 경우 serialization의 호환성을 테스트 합니다. 이 경우에는 새 버전을 이전 버전으로 deserialize하거나 이전 버전을 새 버전으로 deserialize하십시오.  
  
 **✓ CONSIDER** 구현 <xref:System.Runtime.Serialization.IExtensibleDataObject> 형식의 서로 다른 버전 간 왕복 수 있도록 합니다.  
  
 이 인터페이스를 사용하면 serializer에서 라운드트립하는 동안 데이터가 손실되지 않습니다. <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> 속성은 이후 버전의 현재 버전에서는 알 수 없는 형식에서 모든 데이터를 저장 및 사용 하므로 해당 데이터 멤버에 저장이 없습니다. 이후에 현재 버전 serialize 되 고 이후 버전으로 deserialize를 하는 경우 추가 데이터를 제공 됩니다 serialize 된 스트림에서.  
  
## <a name="supporting-xml-serialization"></a>XML Serialization 지원  
 데이터 계약 Serialization은 기본 (기본값).NET Framework의 serialization 기술 이지만 데이터 계약 Serialization을 지원 하지 않는 serialization 시나리오가 있습니다. 예를 들어 serializer에서 생성하거나 사용하는 XML의 모양을 완전히 제어할 수 있는 권한이 없습니다. 이러한 충분 한 제어가 필요한 경우 XML Serialization을 사용할 수 있으며이 serialization 기술을 지원 하기 위한 형식을 디자인 해야 합니다.  
  
 **X AVOID** 생성 되는 XML의 모양을 제어 하는 매우 강력한 이유가 없다면 형식을 XML Serialization을 위해 특별히 디자인 합니다. 이 serialization 기술은 앞의 섹션에서 설명한 데이터 계약 Serialization으로 대체되었습니다.  
  
 **✓ CONSIDER** 구현는 <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스는 serialize 된 XML의 모양 XML Serialization 특성을 적용 하 여 제공 된 것 보다 더 많은 제어 하려는 경우. 인터페이스의 두 가지 방법 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 고 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, serialize 된 XML 스트림을 완전히 제어할 수 있습니다. 적용 하 여 형식에 대해 생성 되는 XML 스키마를 제어할 수도 있습니다는 `XmlSchemaProviderAttribute`합니다.  
  
## <a name="supporting-runtime-serialization"></a>런타임 Serialization 지원  
 런타임 Serialization에는.NET Remoting에서 사용 하는 기술입니다. .NET Remoting을 사용 하 여 형식에 전송 될 경우 런타임 Serialization을 지원 하는지 확인 해야 합니다.  
  
 적용 하 여 런타임 Serialization에 대 한 기본 지원을 제공할 수 있습니다 합니다 <xref:System.SerializableAttribute>, 고급 시나리오는 간단한 런타임 직렬화 가능 패턴을 구현 하며 (구현 <xref:System.Runtime.Serialization.ISerializable> serialization 생성자를 제공).  
  
 **✓ CONSIDER** 형식을.NET Remoting과 함께 사용 될 경우 런타임 Serialization을 지원 합니다. 예를 들어 합니다 <xref:System.AddIn?displayProperty=nameWithType> 네임 스페이스는.NET Remoting을 간에 교환 된 모든 형식이 `System.AddIn` 추가 기능의 런타임 Serialization을 지원 해야 합니다.  
  
 **✓ CONSIDER** 완벽 하 게 serialization 프로세스 제어 하려는 경우 런타임 직렬화 가능 패턴을 구현 합니다. 데이터가 serialize 또는 deserialize될 때 데이터를 변환하려는 경우를 예로 들 수 있습니다.  
  
 이 패턴은 아주 단순합니다. <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하고, 개체가 deserialize될 때 사용되는 특별한 생성자를 제공하기만 하면 됩니다.  
  
 **✓ DO** serialization 생성자를 보호 하 고 입력 하 고이 예제에 표시 된 대로 정확 하 게 명명 된 두 개의 매개 변수를 제공 합니다.  
  
```csharp
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```
  
 **✓ DO** 구현에서 `ISerializable` 멤버가 명시적으로 합니다.  
  
 **✓ DO** 링크 요청에 적용 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> 구현 합니다. 이렇게 하면만 완전히 신뢰할 수 있는 코어 및 런타임 Serializer 멤버에 액세스할 수 있습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
- [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
