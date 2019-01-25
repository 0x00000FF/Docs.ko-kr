---
title: 형식 매개 변수는 한정자로 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 8ee0fd5822c22da090aa0abee679e2f68e0fc1d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659710"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>형식 매개 변수는 한정자로 사용할 수 없습니다.
프로그래밍 요소가 형식 매개 변수를 포함 하는 한정 문자열 한정 됩니다.  
  
 형식 매개 변수를 제네릭 형식 생성 될 때 제공 된 형식에 대 한 요구 사항을 나타냅니다. 정의 된 특정 형식을 나타내지 않습니다. 정규화 문자열에는 컴파일 타임에 정의 된 요소만 포함 해야 합니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **오류 ID:** BC32098  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  한정 문자열에서 형식 매개 변수를 제거 하거나 정의 된 형식으로 바꿉니다.  
  
2.  자격이 부여 되는 프로그래밍 요소를 찾기 위해 생성된 된 형식을 사용 하는 경우 추가 프로그램 논리를 사용 해야 합니다.  
  
## <a name="see-also"></a>참고자료
- [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)
