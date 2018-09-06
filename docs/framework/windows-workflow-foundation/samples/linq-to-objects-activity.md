---
title: LINQ to Objects 활동
ms.date: 03/30/2017
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
ms.openlocfilehash: fca4a94a951c9713a61914de6ef33e0cbb74f75e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891582"
---
# <a name="linq-to-objects-activity"></a>LINQ to Objects 활동
이 샘플에서는 LINQ to Objects를 사용하여 컬렉션의 요소를 쿼리하는 활동을 만드는 방법을 보여 줍니다.  
  
## <a name="activity-details-for-findincollection"></a>FindInCollection의 활동 세부 정보  
 이 활동을 사용하면 사용자가 LINQ to Objects를 사용하여 메모리에 있는 컬렉션의 요소를 쿼리할 수 있습니다. 결과를 필터링하려면 람다 식 형식의 LINQ 조건자를 제공해야 합니다. 이 활동은 <xref:System.Activities.Statements.AddToCollection%601> 활동과 함께 사용할 수 있습니다.  
  
 다음 표에서는 활동의 속성 및 반환 값에 대해 자세히 설명합니다.  
  
|속성 또는 반환 값|설명|  
|------------------------------|-----------------|  
|`Collection` 속성|소스 컬렉션을 지정하는 필수 속성입니다.|  
|`Predicate` 속성|람다 식 형식으로 컬렉션의 필터를 지정하는 필수 속성입니다.|  
|반환 값|필터링된 컬렉션입니다.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>사용자 지정 활동을 사용하는 코드 샘플  
 다음 코드 예제에서는 `FindInCollection` 사용자 지정 활동을 사용하여 직원 컬렉션에서 `Role` 속성이 `Manager`로 설정되고 `Location` 속성이 `Redmond`로 설정된 모든 행을 찾습니다.  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 다음 코드에서는 사용자 지정 FindInCollection 활동, <xref:System.Activities.Statements.AddToCollection%601> 및 <xref:System.Activities.Statements.ForEach%601> 활동을 사용하여 컬렉션을 직원으로 채우고, 레드먼드에 있으면서 개발자 역할을 가진 모든 직원을 찾은 다음, 결과 목록을 반복하는 워크플로 프로그램을 만드는 방법을 보여 줍니다.  
  
```csharp  
// Create the Linq predicate for the find expression  
  
Func<Employee, bool> predicate = e => e.Role == "DEV" && e.Location.Equals("Redmond");  
  
// Create workflow program  
Activity sampleWorkflow = new Sequence  
{  
    Variables = { employees, devsFromRedmond },  
    Activities =  
    {  
        new Assign<IList<Employee>>  
        {  
            To = employees,  
            Value = new LambdaValue<IList<Employee>>(c => new List<Employee>())  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(1, "Employee 1", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(2, "Employee 2", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(3, "Employee 3", "PM", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(4, "Employee 4", "PM", "China"))  
        },  
        new FindInCollection<Employee>  
        {  
            Collections = new InArgument<IEnumerable<Employee>>(employees),  
            Predicate = new LambdaValue<Func<Employee, bool>>(c => predicate),  
            Result = new OutArgument<IList<Employee>>(devsFromRedmond)  
        },  
        new ForEach<Employee>  
        {  
            Values = new InArgument<IEnumerable<Employee>>(devsFromRedmond),  
            Body = new ActivityAction<Employee>  
            {  
                Argument = iterationVariable,  
                Handler = new WriteLine  
                {  
                    Text = new InArgument<string>(env => iterationVariable.Get(env).ToString())  
                }  
            }  
        }  
    }  
};  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 LinqToObjects.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a>참고 항목  
 [람다 식 (C# 프로그래밍 가이드)](https://go.microsoft.com/fwlink/?LinkId=150381)  
 [LINQ to Objects](https://go.microsoft.com/fwlink/?LinkID=150380)
