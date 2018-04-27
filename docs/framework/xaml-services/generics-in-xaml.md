---
title: XAML의 제네릭
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: 8
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e64224edcb49d5040332b7cef9649c98cf26798b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="generics-in-xaml"></a>XAML의 제네릭
System.Xaml에 구현 된 대로.NET Framework XAML 서비스 제네릭 CLR 형식 사용에 대 한 지원을 제공 합니다. 이 지원 형식 인수로 제네릭의 제약 조건을 지정 하는 제약 조건을 적절 한 호출 하 여 적용 및 포함 `Add` 방법의 경우 제네릭 컬렉션입니다. 이 항목에서는 사용 하 고 XAML의 제네릭 형식 참조의 측면을 설명 합니다.  
  
## <a name="xtypearguments"></a>나온  
 `x:TypeArguments` 지시문은 XAML 언어에 의해 정의 됩니다. 제네릭 형식에 의해 지원 되는 XAML 형식의 멤버로 사용할 경우 `x:TypeArguments` 형식 제네릭을 지원 생성자의 인수를 전달 합니다. .NET Framework XAML 서비스에 관련 된 참조 구문이 사용 하 여의 `x:TypeArguments`, 구문 예제를 포함 된, 참조 [X:typearguments 지시문](../../../docs/framework/xaml-services/x-typearguments-directive.md)합니다.  
  
 때문에 `x:TypeArguments` 는 문자열을 형식 변환기 지원을 갖고 특성으로 XAML 사용에 일반적으로 선언 된 것입니다.  
  
 XAML 노드 스트림의 정보에서 선언 `x:TypeArguments` 에서 가져올 수 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 에 `StartObject` 노드 스트림 내의 위치입니다. 반환 값 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 목록이 <xref:System.Xaml.XamlType> 값입니다. XAML 형식 제네릭 형식을 나타내는지 여부를 결정을 호출 하 여 만들어질 수 <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>합니다.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>규칙 및 XAML의 제네릭에 대 한 구문 표기 규칙  
 XAML에서는 제한 된 제네릭으로; 제네릭 형식을 표현 항상 합니다. 제네릭은 XAML 노드 스트림을 또는 XAML 형식 시스템에 존재 하 고 XAML 태그에 나타낼 수 없습니다. 제네릭에서 참조 하 고 제네릭의 중첩된 형식 제약 하는 경우에 대 한 XAML 특성 구문에서 참조할 수 `x:TypeArguments`, 경우 여기서 `x:Type` 제네릭 형식에 대 한 CLR 형식 참조를 제공 합니다. 이 통해 지원 되는 <xref:System.Xaml.Schema.XamlTypeTypeConverter> .NET Framework XAML 서비스에 의해 정의 된 클래스입니다.  
  
 XAML 특성으로 사용 하도록 설정 하는 구문 형식 <xref:System.Xaml.Schema.XamlTypeTypeConverter> 변경 하는 일반적인 MSIL / 각도 사용 하 여 CLR 구문 규칙 유형 및 제네릭, 제약 조건에 대 한 괄호 및 제약 조건 컨테이너에 대 한 괄호를 대신 합니다. 예를 들어 참조 [X:typearguments 지시문](../../../docs/framework/xaml-services/x-typearguments-directive.md)합니다.  
  
## <a name="generics-and-xaml-2009-features"></a>제네릭 및 XAML 2009 기능  
 XAML 2009를 사용 하면 CLR 매핑하는 대신 기본 공용 언어 기본 형식에 대 한 XAML 형식을 가져올 형식을 사용할 수 있습니다 [XAML 2009의 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) 의 정보 항목으로 `x:TypeArguments`합니다. 예를 들어, 다음에 선언할 수 있습니다 (접두사 매핑이 표시 되지 않지만 `x` 은 XAML 언어 XAML 네임 스페이스에 대 한 XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>WPF 및 다른 v3.5 프레임 워크의 제네릭 지원  
 구체적으로 WPF를 대상으로 할 때 XAML 2006 사용에 대 한 [X:class](../../../docs/framework/xaml-services/x-class-directive.md) 와 동일한 요소에도 제공 해야 `x:TypeArguments`, 해당 요소는 XAML 문서의 루트 요소 여야 합니다. 루트 요소는 하나 이상의 형식 인수가 있는 제네릭 형식에 매핑되어야 합니다. 예로 <xref:System.Windows.Navigation.PageFunction%601>합니다.  
  
 가능한 해결 방법에 제네릭 사용을 지 원하는 제네릭 형식을 반환할 수 있는 사용자 지정 태그 확장을 정의 하거나는 래핑 제공 포함 클래스는 제네릭 형식에서 파생 되지만 클래스 정의 자체에서 제네릭 제약 조건을 평평 하 게 정의 합니다.  
  
 WPF와 대상 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]와 함께 XAML 2009 기능을 사용할 수 있습니다 `x:TypeArguments`, 느슨한 XAML (태그 컴파일되지 않은 XAML)에 대해서만 합니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  
  
 Windows Workflow foundation에 대 한 사용자 지정 워크플로 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 일반 XAML 사용을 지원 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [x:TypeArguments 지시문](../../../docs/framework/xaml-services/x-typearguments-directive.md)  
 [x:Class 지시문](../../../docs/framework/xaml-services/x-class-directive.md)  
 [공용 XAML 언어 기본 형식에 대한 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
