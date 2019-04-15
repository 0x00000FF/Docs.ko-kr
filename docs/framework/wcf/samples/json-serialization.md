---
title: JSON serialization
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: bb38005c02e9b3e850282d2a81c2e17143657025
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305288"
---
# <a name="json-serialization"></a>JSON serialization
이 샘플에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 JavaScript Object Notation(JSON) 형식으로 데이터를 serialize 및 deserialize하는 방법을 보여 줍니다. 이 serialization 엔진에서는 JSON 데이터를 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식의 인스턴스로 변환하고 다시 JSON 데이터로 변환합니다. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 와 동일한 형식을 지 원하는 <xref:System.Runtime.Serialization.DataContractSerializer>합니다. JSON 데이터 형식은 AJAX(Asynchronous JavaScript and XML) 스타일 웹 응용 프로그램을 작성하는 경우에 특히 유용합니다. AJAX 지원 Windows Communication Foundation (WCF)에 ScriptManager 컨트롤을 통해 ASP.NET AJAX와 함께 사용 하기 위해 최적화 됩니다. ASP.NET AJAX와 함께 Windows Communication Foundation (WCF)를 사용 하는 방법의 예 참조는 [AJAX 샘플](ajax.md)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 샘플에서는 `Person` 데이터 계약을 사용하여 serialization 및 deserialization을 보여 줍니다.  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 `Person` 형식의 인스턴스를 JSON으로 serialize하려면 먼저 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 만들고 `WriteObject` 메서드를 사용하여 스트림에 JSON 데이터를 기록합니다.  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 메모리 스트림에는 유효한 JSON 데이터가 포함되어 있습니다.
  
```json  
{"age":42,"name":"John"}  
```  
  
 샘플에서는 JSON 데이터에서 개체로의 deserialization을 보여 줍니다. 그 후에 스트림을 되감고 `ReadObject`를 호출합니다.  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 `p2` 개체를 확인하면 JSON 데이터가 올바르게 deserialize된 것을 알 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 에 설명 된 대로 JsonSerialization.sln 솔루션을 빌드합니다 [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
2. 결과 콘솔 응용 프로그램을 실행합니다.  
