---
title: 개체 참조
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: 1aa8b1c9d135186dba9e4da75f0c7cb9297d8e5c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185690"
---
# <a name="object-references"></a>개체 참조
이 샘플에서는 서버와 클라이언트 간에 개체를 참조로 전달하는 방법을 보여 줍니다. 샘플에서는 시뮬레이트된 *사교*합니다. 인맥 네트워크는 친구 목록을 포함하는 `Person` 클래스로 구성되며, 이 목록의 친구는 `Person` 클래스의 인스턴스이며 자체적으로도 친구 목록을 가지고 있습니다. 이를 기반으로 개체 그래프가 생성됩니다. 서비스는 이러한 인맥 네트워크에 대한 작업을 노출합니다.  
  
 이 샘플에서 서비스는 IIS(인터넷 정보 서비스)를 통해 호스팅되고 클라이언트는 콘솔 응용 프로그램(.exe)입니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
## <a name="service"></a>서비스  
 `Person` 클래스에는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성이 적용되어 있으며, 클래스를 참조 형식으로 선언하도록 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 필드가 `true`로 설정되어 있습니다. 모든 속성에는 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성이 적용되어 있습니다.  
  
```  
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 `GetPeopleInNetwork` 작업은 `Person` 형식의 매개 변수를 받아 인맥 네트워크의 모든 사람, 즉 `friends` 목록에 있는 모든 사람과 친구의 친구 등을 중복되는 항목 없이 반환합니다.  
  
```  
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 `GetMutualFriends` 작업은 `Person` 형식의 매개 변수를 받아 서로의 `friends` 목록에 동시에 존재하는 모든 친구를 반환합니다.  
  
```  
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 `GetCommonFriends` 작업은 `Person` 형식의 목록을 사용합니다. 이 목록에는 두 개의 `Person` 개체가 있어야 합니다. 이 작업은 입력 목록에 있는 두 `Person` 개체 모두의 `friends` 목록에 있는 `Person` 개체의 목록을 반환합니다.  
  
```  
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a>클라이언트  
 클라이언트 프록시를 사용 하 여 만들어집니다 합니다 **서비스 참조 추가** Visual Studio의 기능입니다.  
  
 5개의 `Person` 개체로 구성된 인맥 네트워크가 생성됩니다. 클라이언트는 서비스의 메서드 3개를 각각 호출합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 [상호 운영 가능한 개체 참조](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
