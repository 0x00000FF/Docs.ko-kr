---
title: "CodeActivity 클래스를 사용하여 워크플로 활동 제작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f9894926ba93461d332eaac248c71d20ea4e7d30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>CodeActivity 클래스를 사용하여 워크플로 활동 제작
<xref:System.Activities.CodeActivity>에서 상속하여 만들어진 활동은 <xref:System.Activities.CodeActivity.Execute%2A> 메서드를 재정의하여 기본 명령형 동작을 구현합니다.  
  
## <a name="using-codeactivitycontext"></a>CodeActivityContext 사용  
 <xref:System.Activities.CodeActivity.Execute%2A> 형식의 `context` 매개 변수 멤버를 사용하여 <xref:System.Activities.CodeActivityContext> 메서드에서 워크플로 런타임 기능에 액세스할 수 있습니다. <xref:System.Activities.CodeActivityContext>를 통해 사용할 수 있는 기능은 다음과 같습니다.  
  
-   변수와 인수의 값 가져오기 및 설정  
  
-   <xref:System.Activities.CodeActivityContext.Track%2A>을 사용하는 사용자 지정 추적 기능  
  
-   <xref:System.Activities.CodeActivityContext.GetProperty%2A>을 사용하여 활동의 실행 속성에 액세스  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>CodeActivity에서 상속되는 사용자 지정 활동을 만들려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 엽니다.  
  
2.  선택 **파일**, **새**, 차례로 **프로젝트**합니다. 선택 **Workflow 4.0** 아래 **Visual C#** 에 **프로젝트 형식** 창과 선택은 **v2010** 노드. 선택 **활동 라이브러리** 에 **템플릿** 창. 새 프로젝트의 이름을 HelloActivity로 지정합니다.  
  
3.  HelloActivity 프로젝트에서 Activity1.xaml을 마우스 오른쪽 단추로 클릭 하 고 선택 **삭제**합니다.  
  
4.  HelloActivity 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가** , 차례로 **클래스**합니다. 새 프로젝트의 이름을 HelloActivity.cs로 지정합니다.  
  
5.  HelloActivity.cs 파일에서 다음 `using` 지시문을 추가합니다.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  기본 클래스를 클래스 선언에 추가하여 새 클래스를 <xref:System.Activities.CodeActivity>에서 상속하도록 설정합니다.  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  <xref:System.Activities.CodeActivity.Execute%2A> 메서드를 추가하여 클래스에 기능을 추가합니다.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  <xref:System.Activities.CodeActivityContext>를 사용하여 추적 레코드를 만듭니다.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
    ```
