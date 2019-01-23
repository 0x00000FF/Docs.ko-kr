---
title: '방법: Char 값 (Visual Basic)으로 이루어진 배열로 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: a067474d6b32589a34b031d5c3ea4e5a4be55834
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611464"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>방법: Char 값 (Visual Basic)으로 이루어진 배열로 문자열 만들기
이 예제에서는 개별 문자에서 문자열 "abcd"를 만듭니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 메서드는 특수 요구 사항이 없습니다.  
  
 구문을 `"a"c`, 여기서는 단일 `c` 단일 문자를 인용 부호로 같이 리터럴 문자를 만드는 데 사용 됩니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 Null 문자 (같음 `Chr(0)`) 문자열에서 예기치 않은 결과가 나타날 문자열을 사용 하는 경우. Null 문자 문자열에 포함 됩니다. 하지만 null 문자 다음 상황에 따라 표시 되지 않습니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.String>
- [Char 데이터 형식](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
