---
title: 기본 활동을 사용하는 사용자 지정 복합
ms.date: 03/30/2017
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
ms.openlocfilehash: 2b922ef721ab4d125f390e908eb8ea4d3b087035
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142799"
---
# <a name="custom-composite-using-native-activity"></a>기본 활동을 사용하는 사용자 지정 복합
이 샘플에서는 다른 <xref:System.Activities.NativeActivity> 개체가 워크플로 실행 흐름을 제어하도록 예약하는 <xref:System.Activities.Activity>를 작성하는 방법을 보여 줍니다. 이 샘플에서는 두 개의 일반적인 제어 흐름인 Sequence와 While을 사용하여 이러한 작업 수행 방법을 보여 줍니다.

## <a name="sample-details"></a>샘플 세부 정보
 `MySequence`는 <xref:System.Activities.NativeActivity>에서 파생되며, <xref:System.Activities.NativeActivity>는 <xref:System.Activities.Activity> 메서드에 전달된 <xref:System.Activities.NativeActivityContext>를 통해 전체 워크플로 런타임을 노출하는 `Execute` 개체입니다.

 `MySequence`는 워크플로 작성자가 채우는 <xref:System.Activities.Activity> 개체의 공용 컬렉션을 노출합니다. 워크플로가 실행되기 전에 워크플로 런타임은 워크플로의 각 활동에 대해 <xref:System.Activities.Activity.CacheMetadata%2A> 메서드를 호출합니다. 이 프로세스가 진행되는 중에 런타임은 데이터 범위 지정 및 수명 주기 관리를 위해 부모-자식 관계를 설정합니다. <xref:System.Activities.Activity.CacheMetadata%2A> 메서드의 기본 구현은 <xref:System.ComponentModel.TypeDescriptor> `MySequence` 활동에 대한 인스턴스 클래스를 사용하여 형식 <xref:System.Activities.Activity> <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Activity> 또는> `MySequence` 대한 공용 속성을 활동의 자식으로 추가합니다.

 활동에서 자식 활동의 공용 컬렉션을 노출할 때마다 해당 자식 활동이 상태를 공유할 가능성이 큽니다. 이 경우 부모 활동인 `MySequence`는 자식 활동이 이 작업을 수행할 때 사용하는 변수 컬렉션도 노출하는 것이 가장 좋습니다. 자식 활동과 <xref:System.Activities.Activity.CacheMetadata%2A> 마찬가지로 메서드는 <xref:System.Activities.Variable> 형식 <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Variable> 또는> 공용 `MySequence` 속성을 활동과 연관된 변수로 추가합니다.

 `MySequence`는 `MySequence`의 자식이 조작하는 public 변수 외에도 자식의 실행 시 자신의 위치도 추적해야 하며, private 변수인 `currentIndex`를 사용하여 이 작업을 수행합니다. 이 변수는 `MySequence` 활동의 <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> 메서드 내에 있는 `MySequence` 메서드에 대한 호출을 추가하여 <xref:System.Activities.Activity.CacheMetadata%2A> 환경의 일부로 등록됩니다. 컬렉션에 추가된 개체는 <xref:System.Activities.Activity> 이러한 방식으로 추가된 `MySequence` `Activities` 변수에 액세스할 수 없습니다.

 런타임에서 `MySequence`를 실행하면 런타임은 <xref:System.Activities.NativeActivity.Execute%2A> 메서드를 호출하여 <xref:System.Activities.NativeActivityContext>를 전달합니다. <xref:System.Activities.NativeActivityContext>는 다른 <xref:System.Activities.Activity> 개체 또는 `ActivityDelegates`를 예약하고 인수 및 변수를 역참조하기 위해 런타임으로 돌아가는 활동 프록시입니다. `MySequence`는 `InternalExecute` 메서드를 사용하여 첫 번째 자식 및 이후의 모든 자식을 단일 메서드에 예약하는 논리를 캡슐화합니다. `currentIndex`를 역참조하는 작업으로 시작하며, `Activities` 컬렉션에서의 수와 같은 경우 시퀀스가 완료되고 활동은 작업을 예약하지 않고 반환되며 런타임은 <xref:System.Activities.ActivityInstanceState.Closed> 상태로 이동됩니다. `currentIndex` 활동 수가 작으면 다음 `Activities` 자식이 컬렉션 및 호출에서 `MySequence` <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>가져오고 예약할 <xref:System.Activities.CompletionCallback> 자식에 전달하고 메서드를 `InternalExecute` 가리킵니다. 마지막으로 `currentIndex`가 증가하고 제어 권한이 다시 런타임에 제공됩니다. `MySequence`의 인스턴스에 예약된 자식 <xref:System.Activities.Activity> 개체가 있으면 런타임은 해당 개체가 실행 상태에 있는 것으로 간주합니다.

 자식 활동이 완료되면 <xref:System.Activities.CompletionCallback>이 실행됩니다. 루프가 맨 위부터 계속됩니다. `Execute`와 마찬가지로 <xref:System.Activities.CompletionCallback>도 <xref:System.Activities.NativeActivityContext>를 사용하여 구현자에게 런타임에 대한 액세스 권한을 제공합니다.

 `MyWhile``MySequence` 단일 <xref:System.Activities.Activity> 개체를 반복적으로 예약한다는 점에서 다르며, 이 일정이 수행되어야 `Condition` 하는지 여부를 결정하기 위해 명명된 <xref:System.Activities.Activity%601><bool을\> 사용한다는 점에서 다릅니다. `MySequence`와 마찬가지로 `MyWhile`도 `InternalExecute` 메서드를 사용하여 예약 논리를 중앙 집중화합니다. <`Condition` <xref:System.Activities.Activity> \>> 바운더리로 <xref:System.Activities.CompletionCallback%601> \< `OnEvaluationCompleted`일정을 잡습니다. `Condition`의 실행이 완료되면 <xref:System.Activities.CompletionCallback>라는 강력한 형식의 매개 변수에서 이 `result`을 통해 그 결과를 사용할 수 있습니다. `true`이면 `MyWhile`이 <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>을 호출하여 `Body`<xref:System.Activities.Activity> 개체와 `InternalExecute`를 <xref:System.Activities.CompletionCallback>으로 전달합니다. `Body`의 실행이 완료되면 `Condition`에서 `InternalExecute`이 다시 예약되어 루프가 다시 시작됩니다. `Condition`에서 `false`를 반환하면 `MyWhile`의 인스턴스는 `Body`를 예약하지 않고 런타임에 제어 권한을 다시 제공하며 런타임은 <xref:System.Activities.ActivityInstanceState.Closed> 상태로 이동됩니다.

#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면

1. Visual Studio 2010에서 Composite.sln 샘플 솔루션을 엽니다.

2. 솔루션을 빌드하고 실행합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`
