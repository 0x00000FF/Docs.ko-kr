---
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: a42bf12e6ee8275814898a0158348f56bfb2688e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112868"
---
# <a name="datacontractresolver"></a>DataContractResolver
이 샘플에서는 <xref:System.Runtime.Serialization.DataContractResolver> 클래스를 사용하여 serialization 및 deserialization 프로세스를 사용자 지정하는 방법을 보여 줍니다. 이 샘플에서는 DataContractResolver를 사용하여 serialization 및 deserialization 중에 xsi:type 표현에 대한 CLR 형식의 매핑 방법을 보여 줍니다.

## <a name="sample-details"></a>샘플 세부 정보
 이 샘플에서는 다음 CLR 형식을 정의합니다.

```csharp
using System;
using System.Runtime.Serialization;

namespace Types
{
    [DataContract]
    public class Customer
    {
        [DataMember]
        public string Name { get; set; }
    }

    [DataContract]
    public class VIPCustomer : Customer
    {
        [DataMember]
        public string VipInfo { get; set; }
    }

    [DataContract]
    public class RegularCustomer : Customer
    {
    }

    [DataContract]
    public class PreferredVIPCustomer : VIPCustomer
    {
    }
}
```

 이 샘플에서는 어셈블리를 로드하고 어셈블리의 각 형식을 추출한 다음 serialize 및 deserialize합니다. <xref:System.Runtime.Serialization.DataContractResolver>는 다음 예제와 같이 <xref:System.Runtime.Serialization.DataContractResolver> 파생 클래스의 인스턴스를 <xref:System.Runtime.Serialization.DataContractSerializer> 생성자에 전달하여 serialization 프로세스에 연결됩니다.

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 그런 다음 아래의 코드 예제와 같이 CLR 형식을 serialize합니다.

```csharp
Assembly assembly = Assembly.Load(new AssemblyName("Types"));

public void serialize(Type type)
{
    Object instance = Activator.CreateInstance(type);

    Console.WriteLine("----------------------------------------");
    Console.WriteLine();
    Console.WriteLine("Serializing type: {0}", type.Name);
    Console.WriteLine();
    this.buffer = new StringBuilder();
    using (XmlWriter xmlWriter = XmlWriter.Create(this.buffer))
    {
        try
        {
            this.serializer.WriteObject(xmlWriter, instance);
        }
        catch (SerializationException error)
        {
            Console.WriteLine(error.ToString());
        }
    }
    Console.WriteLine(this.buffer.ToString());
}
```

 그런 다음 아래의 코드 예제와 같이 xsi:type을 deserialize합니다.

```csharp
public void deserialize(Type type)
{
    Console.WriteLine();
    Console.WriteLine("Deserializing type: {0}", type.Name);
    Console.WriteLine();
    using (XmlReader xmlReader = XmlReader.Create(new StringReader(this.buffer.ToString())))
    {
        Object obj = this.serializer.ReadObject(xmlReader);
    }
}
```

 사용자 지정 <xref:System.Runtime.Serialization.DataContractResolver>가 <xref:System.Runtime.Serialization.DataContractSerializer> 생성자에 전달되므로 <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A>은 serialization 중에 CLR 형식을 해당하는 `xsi:type`에 매핑하기 위해 호출됩니다. 이와 마찬가지로 <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>은 deserialization 중에 `xsi:type`을 해당하는 CLR 형식에 매핑하기 위해 호출됩니다. 이 샘플에서 <xref:System.Runtime.Serialization.DataContractResolver>는 다음 예제와 같이 정의됩니다.

 다음 코드 예제는 <xref:System.Runtime.Serialization.DataContractResolver>에서 파생되는 클래스입니다.

```csharp
class MyDataContractResolver : DataContractResolver
{
    private Dictionary<string, XmlDictionaryString> dictionary = new Dictionary<string, XmlDictionaryString>();
    Assembly assembly;

    public MyDataContractResolver(Assembly assembly)
    {
        this.assembly = assembly;
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        XmlDictionaryString tName;
        XmlDictionaryString tNamespace;
        if (dictionary.TryGetValue(typeName, out tName) && dictionary.TryGetValue(typeNamespace, out tNamespace))
        {
            return this.assembly.GetType(tNamespace.Value + "." + tName.Value);
        }
        else
        {
            return null;
        }
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        string name = dataContractType.Name;
        string namesp = dataContractType.Namespace;
        typeName = new XmlDictionaryString(XmlDictionary.Empty, name, 0);
        typeNamespace = new XmlDictionaryString(XmlDictionary.Empty, namesp, 0);
        if (!dictionary.ContainsKey(dataContractType.Name))
        {
            dictionary.Add(name, typeName);
        }
        if (!dictionary.ContainsKey(dataContractType.Namespace))
        {
            dictionary.Add(namesp, typeNamespace);
        }
    }
}
```

 샘플에 포함된 Types 프로젝트에서는 이 샘플에 사용되는 모든 형식을 포함하는 어셈블리를 생성합니다. 이 프로젝트를 사용하여 serialize할 형식을 추가, 제거 또는 수정합니다.

#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1.  DCRSample.sln 솔루션 파일을 열고 Visual Studio 2012를 사용 합니다.

2.  F5 키를 눌러 솔루션을 실행합니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a>참고자료

- [데이터 계약 확인자 사용](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)
