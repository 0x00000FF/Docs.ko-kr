---
title: Nullable 형식 boxing(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
ms.openlocfilehash: e2c7602bf45f1861d3a32a73824e9fedf0a4d29d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334758"
---
# <a name="boxing-nullable-types-c-programming-guide"></a>Nullable 형식 boxing(C# 프로그래밍 가이드)
Nullable 형식을 기반으로 하는 개체는 개체가 null이 아닌 경우에만 boxing됩니다. <xref:System.Nullable%601.HasValue%2A>가 `false`이면 boxing 대신 개체 참조가 `null`에 할당됩니다. 예:  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 개체가 null이 아닌 경우(<xref:System.Nullable%601.HasValue%2A>가 `true`인 경우) boxing이 발생하지만 nullable 개체의 기반이 되는 기본 형식만 boxing됩니다. null이 아닌 nullable 값 형식을 boxing하면 값 형식을 래핑하는 <xref:System.Nullable%601?displayProperty=nameWithType>이 아니라 값 형식 자체가 boxing됩니다. 예:  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 두 boxed 개체는 nullable이 아닌 형식을 boxing하여 만들어진 개체와 동일합니다. 또한 nullable이 아닌 boxed 형식과 마찬가지로, 다음 예제와 같이 nullable 형식으로 unboxed할 수 있습니다.  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>설명  
 boxed 시 nullable 형식의 동작은 다음 두 가지 이점을 제공합니다.  
  
1.  nullable 개체 및 boxed 상대 항목이 null인지 테스트할 수 있습니다.  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  boxed nullable 형식은 기본 형식의 기능을 완벽하게 지원합니다.  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)  
 [방법: Nullable 형식 식별](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
