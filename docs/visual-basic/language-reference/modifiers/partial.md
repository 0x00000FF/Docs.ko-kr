---
title: Partial(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: e1464421866ee22f27f9cf0a3611bc09a631c004
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975838"
---
# <a name="partial-visual-basic"></a>Partial(Visual Basic)
형식 선언이 해당 형식에 대한 부분 정의임을 나타냅니다.  
  
 
  `Partial` 키워드를 사용하여 형식 정의를 다수의 선언으로 나눌 수 있습니다. 원하는 만큼 다양한 소스 파일에서 원하는 만큼 partial 선언을 사용할 수 있습니다. 그러나 모든 선언이 동일한 어셈블리와 동일한 네임스페이스에 있어야 합니다.  
  
> [!NOTE]
>  Visual Basic에서는 *부분 메서드*, 하는 속성은 일반적으로 partial 클래스에서 구현 됩니다. 자세한 내용은 [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) 하 고 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attrlist`|선택 사항입니다. 이 형식에 적용되는 특성의 목록입니다. 묶어야 합니다 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 (`< >`).|  
|`accessmodifier`|선택 사항입니다. 이 형식에 액세스할 수 있는 코드를 지정합니다. [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.|  
|`Shadows`|선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.|  
|`MustInherit`|선택 사항입니다. 참조 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)합니다.|  
|`NotInheritable`|선택 사항입니다. 참조 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)합니다.|  
|`name`|필수 요소. 이 형식의 이름입니다. 동일한 형식의 다른 모든 partial 선언에 정의된 이름과 일치해야 합니다.|  
|`Of`|선택 사항입니다. 제네릭 형식임을 지정합니다. 참조 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)합니다.|  
|`typelist`|사용 하는 경우 필요 [의](../../../visual-basic/language-reference/statements/of-clause.md)합니다. 참조 [유형 목록](../../../visual-basic/language-reference/statements/type-list.md)합니다.|  
|`Inherits`|선택 사항입니다. 참조 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)합니다.|  
|`classname`|
  `Inherits`를 사용하는 경우 필수입니다. 이 클래스가 파생되는 출처인 인터페이스 또는 클래스의 이름입니다.|  
|`Implements`|선택 사항입니다. 참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.|  
|`interfacenames`|
  `Implements`를 사용하는 경우 필수입니다. 이 형식이 구현하는 인터페이스의 이름입니다.|  
|`variabledeclarations`|선택 사항입니다. 형식에 대한 추가 변수 및 이벤트를 선언하는 문입니다.|  
|`proceduredeclarations`|선택 사항입니다. 형식에 대한 추가 프로시저를 선언하고 정의하는 문입니다.|  
|`End Class` 또는 `End Structure`|
  `Class` 또는 `Structure`에 대한 이 부분적 정의를 종료합니다.|  
  
## <a name="remarks"></a>설명  
 Visual Basic에서는 사용자가 별도의 소스 파일에서 작성한 코드에서 생성된 코드를 구분하는 데 partial 클래스 정의를 사용합니다. 예를 들어, **Windows Form 디자이너**에서는 <xref:System.Windows.Forms.Form>과 같은 컨트롤에 대해 partial 클래스를 정의합니다. 이런 컨트롤에서 생성된 코드를 수정해서는 안 됩니다.  
  
 부분 형식(Partial Type)을 만들면 클래스, 구조체, 인터페이스 및 모듈 만들기에 대한 모든 규칙(예; 한정자 사용 및 상속에 대한 규칙)이 적용됩니다.  
  
## <a name="best-practices"></a>모범 사례  
  
-   일반적인 상황에서는 단일 형식의 개발을 두 개 이상의 선언으로 분할해서는 안 됩니다. 따라서 대부분의 경우 `Partial` 키워드가 필요 없습니다.  
  
-   가독성을 위해, 형식에 대한 모든 partial 선언에는 `Partial` 키워드를 포함해야 합니다. 컴파일러는 최대 하나의 partial 선언에서 이 키워드가 생략되는 것을 허용합니다. 두 개 이상의 partial 선언에서 이를 생략하는 경우 컴파일러에서 오류를 알립니다.  
  
## <a name="behavior"></a>동작  
  
-   **선언의 합집합입니다.** 컴파일러는 이 형식을 모든 partial 선언의 공용 구조체로 처리합니다. 모든 부분 정의의 모든 한정자는 전체 형식에 적용되며, 모든 부분 정의의 모든 멤버를 전체 형식에 사용할 수 있습니다.  
  
-   **형식 승격 부분 형식 모듈에 대 한 허용 되지 않습니다.** 모듈 내부에 부분 정의가 있는 경우 해당 형식의 형식 승격은 자동으로 무효화됩니다. 이러한 경우 일련의 부분 정의로 인해 예기치 않은 결과뿐만 아니라 컴파일러 오류도 발생할 수 있습니다. 자세한 내용은 [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)합니다.  
  
     컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.  
  
 
  `Partial` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 클래스 `sampleClass`의 정의를 두 개의 선언으로 분할합니다(여기서 각 선언은 서로 다른 `Sub` 프로시저를 정의함).  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 앞의 예제에서 두 개의 부분 정의는 동일한 소스 파일에 있거나 두 개의 서로 다른 소스 파일에 있을 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)
- [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
