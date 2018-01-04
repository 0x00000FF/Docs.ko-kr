---
title: "While 활동의 열거 중단"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22a03c2e7dcc8d024ed407e7df24a4e9db4e2bf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="emulating-breaking-in-a-while-activity"></a>While 활동의 열거 중단
이 샘플에서는 <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While> 및 <xref:System.Activities.Statements.ParallelForEach%601> 활동의 루프 메커니즘을 중단하는 방법을 보여 줍니다.  
  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]에는 이러한 루프의 실행을 중단하는 활동이 전혀 포함되어 있지 않으므로 이와 같은 방법이 유용할 수 있습니다.  
  
## <a name="scenario"></a>시나리오  
 이 샘플에서는 `Vendor` 클래스의 인스턴스인 공급업체 목록 중 신뢰할 수 있는 첫째 공급업체를 찾습니다. 각 공급업체에는 `ID`와 `Name` 및 공급업체의 신뢰도를 나타내는 숫자 값이 있습니다. 이 샘플에서는 공급업체 목록과 최소 신뢰도 값을 나타내는 입력 매개 변수 두 개를 받고 목록 중 지정된 조건에 일치하는 첫째 공급업체를 반환하는 `FindReliableVendor`라는 사용자 지정 활동을 만듭니다.  
  
## <a name="breaking-a-loop"></a>루프 중단  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]에는 루프를 중단하는 활동이 포함되어 있지 않습니다. 이 코드 샘플에서는 <xref:System.Activities.Statements.If> 활동과 여러 가지 변수를 사용하여 루프를 중단합니다. 이 샘플에서 <xref:System.Activities.Statements.While> 변수에 `reliableVendor`이 아닌 다른 값이 할당되면 `null` 활동이 중단됩니다.  
  
 다음 코드 예제에서는 이 샘플을 통해 while 루프가 어떻게 중단되는지 보여 줍니다.  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 EmulatingBreakInWhile.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`