---
title: 클래스, 구조체 및 인터페이스의 이름
ms.date: 03/30/2017
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c56f840bc5ebd5070c9b686384751acab3f0203
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706075"
---
# <a name="names-of-classes-structs-and-interfaces"></a>클래스, 구조체 및 인터페이스의 이름
명명 지침을 따르는 일반 형식 이름에 적용 됩니다.  
  
 **✓ DO** 명사 또는 명사구를 PascalCasing를 사용 하 여으로 클래스 및 구조체 이름을 지정 합니다.  
  
 이 메서드의 동사구를 사용 하 여 명명 된 형식 이름을 구분 합니다.  
  
 **✓ DO** 형용사 구 또는 경우에 따라 명사 또는 명사구 인터페이스 이름을 지정 합니다.  
  
 명사 및 명사구를 거의 사용 해야 하며 형식을 추상 클래스와 인터페이스 하지 되어야 함을 나타낼 수 있습니다.  
  
 **X DO NOT** 클래스 이름 (예: "C")는 접두사를 제공 합니다.  
  
 **✓ CONSIDER** 기본 클래스의 이름으로 클래스를 파생 종료 이름입니다.  
  
 이 매우 읽기가 가능 하며 명확 하 게 관계에 설명 합니다. 이 코드의 예로: `ArgumentOutOfRangeException`는 일종의 `Exception`, 및 `SerializableAttribute`, 종류는의 `Attribute`. 그러나 반드시이 지침은; 적용할 합리적인 판단을 사용 하 여 예를 들어 합니다 `Button` 클래스는 일종의 `Control` 이벤트 있지만 `Control` 이름에 표시 되지 않습니다.  
  
 **✓ DO** 문자로 접두사 인터페이스 이름을 I, 유형을 인터페이스 임을 나타냅니다.  
  
 예를 들어 `IComponent` (설명이 포함 된 명사) `ICustomAttributeProvider` (명사구) 및 `IPersistable` (명사)은 적절 한 인터페이스 이름입니다. 다른 형식 이름과 마찬가지로 약어를 방지 합니다.  
  
 **✓ DO** 이름으로 "I" 접두사 인터페이스 이름에는 클래스는 인터페이스의 표준 구현 클래스-인터페이스 쌍을 정의 하는 경우에 다른 지 확인 합니다.  
  
## <a name="names-of-generic-type-parameters"></a>제네릭 형식 매개 변수 이름  
 제네릭은은.NET Framework 2.0에 추가 되었습니다. 기능 도입 라는 식별자의 새 종류 *형식 매개 변수*합니다.  
  
 **✓ DO** 단일 문자 이름을 완전히 자체 설명 하 고 설명 하는 이름 값을 더 하지 않는 경우 제외 설명적인 이름으로 name 제네릭 형식 매개 변수입니다.  
  
 **✓ CONSIDER** 를 사용 하 여 `T` 단일 문자 형식 매개 변수를 사용 하는 형식에 대 한 형식 매개 변수 이름으로 합니다.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** 설명적인 형식 매개 변수 이름 앞에 `T`합니다.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 **✓ CONSIDER** 제약 조건을 나타내는 매개 변수 이름의 형식 매개 변수에 적용 합니다.  
  
 매개 변수를 제한 하는 예를 들어 `ISession` 이라고 할 수 있습니다 `TSession`합니다.  
  
## <a name="names-of-common-types"></a>공용 형식의 이름  
 **✓ DO** 또는 특정.NET Framework 형식이 구현에서 파생 된 형식의 이름을 지정할 때 다음 표에 설명 된 지침을 따르십시오.  
  
|Base Type|파생 된 구현 형식 지침|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** 사용자 지정 특성 클래스의 이름에 "특성" 접미사를 추가 합니다.|  
|`System.Delegate`|**✓ DO** 이벤트에 사용 되는 대리자의 이름에 "EventHandler" 접미사를 추가 합니다.<br /><br /> **✓ DO** 이외의 이벤트 처리기로 사용 되는 접미사 "Callback" 이름에 대리자를 추가 합니다.<br /><br /> **X DO NOT** "대리자" 접미사는 대리자를 추가 합니다.|  
|`System.EventArgs`|**✓ DO** "EventArgs입니다." 접미사 추가|  
|`System.Enum`|**X DO NOT** 대신 해당 언어에서 지 원하는 키워드를 사용 하 여; 예를 들어 C#에서 사용 하 여이 클래스에서 파생 된 `enum` 키워드입니다.<br /><br /> **X DO NOT** "열거형" 또는 "Flag" 접미사 추가|  
|`System.Exception`|**✓ DO** "예외" 접미사 추가|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** "사전입니다." 접미사 추가 `IDictionary` 는 컬렉션의 특정 형식 이지만이 지침은 보다 일반적인 컬렉션 지침 보다 우선 합니다.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** "Collection" 접미사 추가|  
|`System.IO.Stream`|**✓ DO** "스트림입니다." 접미사 추가|  
|`CodeAccessPermission IPermission`|**✓ DO** "권한" 접미사 추가|  
  
## <a name="naming-enumerations"></a>열거형 이름 지정  
 일반적 열거형 형식 (열거형이 라고도 함)의 이름은 표준 형식 명명 규칙 (PascalCasing 등) 따라야 합니다. 그러나 열거형에 특별히 적용 되는 추가 사용 지침이 있습니다.  
  
 **✓ DO** 비트 필드에 해당 값이 경우가 아니면 열거형에 대 한 단수형 형식 이름을 사용 합니다.  
  
 **✓ DO** 라고도 함 플래그 열거형 값으로 비트 필드 열거형에 대 한 복수 형식 이름을 사용 합니다.  
  
 **X DO NOT** enum 형식 이름에 "열거형" 접미사를 사용 합니다.  
  
 **X DO NOT** "플래그를"를 사용 하 여 또는 열거형에서 "Flags" 접미사 이름을 입력 합니다.  
  
 **X DO NOT** 서식 있는 텍스트 열거형 등에 대 한 열거형 값 이름 (예: "ad" 열거형의 ADO.), "rtf"에 접두사를 사용 합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참고자료

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
- [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
