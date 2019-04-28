---
title: 활동 확장 사용
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: e524f7e7127eb215be85b0c317474eee70830c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669513"
---
# <a name="using-activity-extensions"></a>활동 확장 사용
활동은 호스트에서 워크플로에 명시적으로 모델링되지 않은 추가 기능을 제공할 수 있도록 하는 워크플로 응용 프로그램 확장과 상호 작용할 수 있습니다.  이 항목에서는 활동이 실행되는 횟수를 계산하기 위해 확장을 만들고 사용하는 방법을 설명합니다.

### <a name="to-use-an-activity-extension-to-count-executions"></a>활동 확장을 사용하여 실행 횟수를 계산하려면

1. Visual Studio 2010을 엽니다. 선택 **새**하십시오 **프로젝트**합니다. 아래는 **Visual C#** 노드를 선택 **워크플로**합니다.  선택 **워크플로 콘솔 응용 프로그램** 템플릿 목록에서. 프로젝트 이름을 `Extensions`로 지정합니다. **확인**을 클릭해 프로젝트를 만듭니다.

2. 추가 된 `using` 문을 Program.cs 파일에는 **System.Collections.Generic** 네임 스페이스.

    ```
    using System.Collections.Generic;
    ```

3. Program.cs 파일에서 라는 새 클래스를 만듭니다 **ExecutionCountExtension**합니다. 다음 코드에서는 인스턴스 Id를 추적 하는 워크플로 확장 경우 해당 **등록** 메서드가 호출 됩니다.

    ```
    // This extension collects a list of workflow Ids
    public class ExecutionCountExtension
    {
        IList<Guid> instances = new List<Guid>();

        public int ExecutionCount
        {
            get
            {
                return this.instances.Count;
            }
        }

        public IEnumerable<Guid> InstanceIds
        {
            get
            {
                return this.instances;
            }
        }

        public void Register(Guid activityInstanceId)
        {
            if (!this.instances.Contains<Guid>(activityInstanceId))
            {
                instances.Add(activityInstanceId);
            }
        }
    }
    ```

4. 사용 하는 작업을 만들 합니다 **ExecutionCountExtension**합니다. 다음 코드를 검색 하는 동작을 정의 합니다 **ExecutionCountExtension** 개체는 런타임 및 호출에서 해당 **등록** 메서드 작업을 실행할 때.

    ```
    // Activity that consumes an extension provided by the host. If the extension is available
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)
    public class MyActivity: CodeActivity
    {
        protected override void Execute(CodeActivityContext context)
        {
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();
            if (ext != null)
            {
                ext.Register(context.WorkflowInstanceId);
            }

        }
    }
    ```

5. 활동을 구현 합니다 **Main** program.cs 파일의 메서드. 다음 코드에는 두 가지 워크플로를 생성하고 각 워크플로를 몇 번 실행하며 확장에 포함된 결과 데이터를 표시하는 메서드가 포함되어 있습니다.

    ```
    class Program
    {
        // Creates a workflow that uses the activity that consumes the extension
        static Activity CreateWorkflow1()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity()
                }
            };
        }

        // Creates a workflow that uses two instances of the activity that consumes the extension
        static Activity CreateWorkflow2()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity(),
                    new MyActivity()
                }
            };
        }

        static void Main(string[] args)
        {
            // create the extension
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();

            // configure the first invoker and execute 3 times
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());
            invoker.Extensions.Add(executionCountExt);
            invoker.Invoke();
            invoker.Invoke();
            invoker.Invoke();

            // configure the second invoker and execute 2 times
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());
            invoker2.Extensions.Add(executionCountExt);
            invoker2.Invoke();
            invoker2.Invoke();

            // show the data in the extension
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));
        }
    }
    ```
