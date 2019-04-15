---
title: NetDataContractSerializer의 기능을 공급하기 위해 DataContractSerializer 및 DataContractResolver를 사용
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 0378f8d6e21f44eb1f39e9ebf51ef0dfaf8d8e8a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295148"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a>NetDataContractSerializer의 기능을 공급하기 위해 DataContractSerializer 및 DataContractResolver를 사용
이 샘플에서는 <xref:System.Runtime.Serialization.DataContractSerializer>와 적절한 <xref:System.Runtime.Serialization.DataContractResolver>를 함께 사용하여 <xref:System.Runtime.Serialization.NetDataContractSerializer>와 동일한 기능을 제공하는 방법을 보여 줍니다. 이를 위해 적절한 <xref:System.Runtime.Serialization.DataContractResolver>를 만드는 방법과 이를 <xref:System.Runtime.Serialization.DataContractSerializer>에 추가하는 방법을 보여 줍니다.

## <a name="sample-details"></a>샘플 세부 정보
 <xref:System.Runtime.Serialization.NetDataContractSerializer> 다른 <xref:System.Runtime.Serialization.DataContractSerializer> 중요 한 한 가지에서: <xref:System.Runtime.Serialization.NetDataContractSerializer> 반면 serialize 된 XML을 CLR 형식 정보에 <xref:System.Runtime.Serialization.DataContractSerializer> 하지 않습니다. 따라서 serialize하는 쪽과 deserialize하는 쪽이 모두 동일한 CLR 형식을 공유하는 경우에만 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용할 수 있습니다. 그러나 <xref:System.Runtime.Serialization.DataContractSerializer>는 <xref:System.Runtime.Serialization.NetDataContractSerializer>보다 성능이 우수하므로 이를 사용하는 것이 좋습니다. <xref:System.Runtime.Serialization.DataContractSerializer>에서는 <xref:System.Runtime.Serialization.DataContractResolver>를 추가하여 serialize되는 정보를 변경할 수 있습니다.

 이 샘플은 두 프로젝트로 구성되어 있습니다. 첫 번째 프로젝트에서는 <xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용하여 개체를 serialize합니다. 두 번째 프로젝트에서는 <xref:System.Runtime.Serialization.DataContractSerializer>와 <xref:System.Runtime.Serialization.DataContractResolver>를 함께 사용하여 첫 번째 프로젝트와 동일한 기능을 제공합니다.

 다음 코드 예제에서는 DCSwithDCR 프로젝트의 <xref:System.Runtime.Serialization.DataContractResolver>에 추가된 `MyDataContractResolver`라는 사용자 지정 <xref:System.Runtime.Serialization.DataContractSerializer>의 구현을 보여 줍니다.

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        if (type == null)
        {
            type = Type.GetType(typeName + ", " + typeNamespace);
        }
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. DCRSample.sln 솔루션 파일을 열고 Visual Studio 2012를 사용 합니다.

2. 솔루션 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.

3. 에 **솔루션 속성 페이지** 대화 상자 아래에 있는 **공용 속성**, **시작 프로젝트**를 선택 **여러 개의 시작 프로젝트:**.

4. 옆에 **DCSwithDCR** 프로젝트 선택 **시작** 에서 **작업** 드롭다운 합니다.

5. 옆에 **NetDCS** 프로젝트 선택 **시작** 에서 **작업** 드롭다운 합니다.

6. 클릭 **확인** 는 대화 상자를 닫습니다.

7. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.

8. Ctrl+F5를 눌러 솔루션을 실행합니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
