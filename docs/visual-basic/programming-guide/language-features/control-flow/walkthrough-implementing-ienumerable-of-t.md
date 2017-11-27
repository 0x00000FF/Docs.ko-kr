---
title: "Visual Basic에서 ienumerable 인터페이스를 구현합니다."
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45b4008f0bf3ae0f303aa029e7bff5b82ab6f259
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>연습: Visual Basic에서 IEnumerable(Of T) 구현
<xref:System.Collections.Generic.IEnumerable%601> 인터페이스는 한 번에 하나의 항목 값의 시퀀스를 반환할 수 있는 클래스에서 구현 됩니다. 데이터를 한 번에 한 항목은 작업을 메모리에 완전 한 데이터 집합을 로드할 필요가 없습니다 반환 활용 합니다. 충분 한 메모리를 사용 하 여 데이터에서 단일 항목을 로드 해야 합니다. 구현 하는 클래스는 `IEnumerable(T)` 인터페이스를 함께 사용할 수 있습니다 `For Each` 루프 또는 LINQ 쿼리 합니다.  
  
 예를 들어 큰 텍스트 파일을 읽고 특정 검색 기준과 일치 하는 파일에서 각 줄을 반환 해야 하는 응용 프로그램을 고려해 야 합니다. 응용 프로그램 LINQ 쿼리를 사용 하 여 지정된 된 조건과 일치 하는 파일의 줄을 반환 합니다. LINQ 쿼리를 사용 하 여 파일의 내용을 퀴리, 응용 프로그램 배열 또는 컬렉션으로는 파일의 내용을 로드할 수 있습니다. 그러나 배열 또는 컬렉션에 전체 파일을 로드 필요한 것 보다 훨씬 더 많은 메모리를 사용 합니다. 대신 LINQ 쿼리 검색 조건과 일치 하는 값만 반환 하는 열거 가능한 클래스를 사용 하 여 파일 내용을 쿼리할 수 있습니다. 일부만 반환 하는 쿼리 훨씬 적은 메모리를 사용할 일치 하는 값입니다.  
  
 구현 하는 클래스를 만들 수는 <xref:System.Collections.Generic.IEnumerable%601> 열거 가능한 데이터와 원본 데이터를 노출 하는 인터페이스입니다. 클래스를 구현 하는 `IEnumerable(T)` 인터페이스를 구현 하는 다른 클래스를 필요로 합니다는 <xref:System.Collections.Generic.IEnumerator%601> 원본 데이터에서 반복 하는 인터페이스입니다. 이러한 두 클래스를 사용 하 여 데이터 항목을 특정 형식으로 순차적으로 반환할 수 있습니다.  
  
 이 연습에서는 구현 하는 클래스를 만듭니다는 `IEnumerable(Of String)` 인터페이스와 구현 하는 클래스는 `IEnumerator(Of String)` 인터페이스를 한 줄씩 텍스트 파일을 한 번에 읽을 수 있습니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>열거 가능한 클래스 만들기  
  
|Enumerable 클래스 프로젝트를 만들려면|  
|---|  
|1.  [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.<br />2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다. **템플릿** 창에서 **클래스 라이브러리**를 선택합니다. **이름** 상자에 `StreamReaderEnumerable`를 입력한 다음 **확인**을 클릭합니다. 새 프로젝트가 표시 됩니다.<br />3.  **솔루션 탐색기**Class1.vb 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **이름 바꾸기**합니다. 파일 이름을 `StreamReaderEnumerable.vb`으로 바꾸고 ENTER 키를 누릅니다. 파일 이름을 바꾸면 클래스 이름도 `StreamReaderEnumerable`으로 바뀝니다. 이 클래스는 `IEnumerable(Of String)` 인터페이스를 구현합니다.<br />4.  StreamReaderEnumerable 프로젝트를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**, 클릭 하 고 **새 항목**합니다. 선택 된 **클래스** 템플릿. 에 **이름** 상자에 입력 합니다 `StreamReaderEnumerator.vb` 클릭 **확인**합니다.|  
  
 이 프로젝트의 첫 번째 클래스의 열거 가능한 클래스 이며 구현는 `IEnumerable(Of String)` 인터페이스입니다. 이 제네릭 인터페이스를 구현 하는 <xref:System.Collections.IEnumerable> 인터페이스와이 클래스의 소비자로 입력 된 값에 액세스할 수 있도록 보증 `String`합니다.  
  
|IEnumerable을 구현 하는 코드를 추가 하려면|  
|---|  
|1.  StreamReaderEnumerable.vb 파일을 엽니다.<br />2.  다음 줄에 `Public Class StreamReaderEnumerable`를 입력 한 다음 ENTER 키를 누릅니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에 필요한 멤버를 사용 하 여 클래스를 자동으로 채우려고는 `IEnumerable(Of String)` 인터페이스입니다.<br />3.  열거 가능한이 클래스는 한 번에는 한 줄씩 텍스트 파일에서에서 줄을 읽습니다. 다음 코드는 파일 경로 입력된 매개 변수로 사용 하는 공용 생성자를 노출 하는 클래스를 추가 합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  구현에서 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 의 메서드는 `IEnumerable(Of String)` 인터페이스의 새 인스턴스를 반환 합니다는 `StreamReaderEnumerator` 클래스입니다. 구현에서 `GetEnumerator` 의 메서드는 `IEnumerable` 인터페이스를 만들 수 있습니다 `Private`의 멤버를 노출 해야 하기 때문에는 `IEnumerable(Of String)` 인터페이스입니다. 코드를 대체 하는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에 대해 생성 된는 `GetEnumerator` 메서드를 다음 코드로 합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|IEnumerator를 구현 하는 코드를 추가 하려면|  
|---|  
|1.  StreamReaderEnumerator.vb 파일을 엽니다.<br />2.  다음 줄에 `Public Class StreamReaderEnumerator`를 입력 한 다음 ENTER 키를 누릅니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에 필요한 멤버를 사용 하 여 클래스를 자동으로 채우려고는 `IEnumerator(Of String)` 인터페이스입니다.<br />3.  열거자 클래스 텍스트 파일이 열리고 파일의 파일에서 줄을 읽을 수는 I/O를 수행 합니다. 클래스는 파일 경로 입력된 매개 변수로 사용 하는 공용 생성자를 노출 하 고 읽기에 대 한 텍스트 파일을 열에 다음 코드를 추가 합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  `Current` 둘 다에 대 한 속성의 `IEnumerator(Of String)` 및 `IEnumerator` 으로 텍스트 파일에서 현재 항목을 반환 하는 인터페이스는 `String`합니다. 구현에서 `Current` 속성의는 `IEnumerator` 인터페이스를 만들 수 있습니다 `Private`의 멤버를 노출 해야 하기 때문에는 `IEnumerator(Of String)` 인터페이스입니다. 코드를 대체 하는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에 대해 생성 된는 `Current` 다음 코드를 사용 하 여 속성입니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  `MoveNext` 의 메서드는 `IEnumerator` 인터페이스 텍스트 파일에서 다음 항목으로 이동 하 고 반환 되는 값을 업데이트 하는 `Current` 속성입니다. 읽기, 더 많은 항목이 없는 경우는 `MoveNext` 메서드 반환 `False`고, 그렇지 않으면는 `MoveNext` 메서드가 반환 되 `True`합니다. `MoveNext` 메서드에 다음 코드를 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  `Reset` 의 메서드는 `IEnumerator` 인터페이스는 반복기를 텍스트 파일의 시작 부분을 가리키도록 지시 하 고 현재 항목 값을 지웁니다. `Reset` 메서드에 다음 코드를 추가합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  `Dispose` 의 메서드는 `IEnumerator` 인터페이스 보장 하는 반복기를 제거 하기 전에 관리 되지 않는 리소스를 모두 해제 됩니다. 사용 되는 파일 핸들은 `StreamReader` 개체는 관리 되지 않는 리소스 반복기 인스턴스를 제거 하기 전에 닫혀 있어야 합니다. 코드를 대체 하는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에 대해 생성 된는 `Dispose` 메서드를 다음 코드로 합니다.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>샘플 반복기 사용  
 열거 가능한 클래스를 사용 하 여 구현 하는 개체를 필요로 하는 제어 구조와 함께 코드에서 `IEnumerable`와 같은 `For Next` 루프 또는 LINQ 쿼리입니다. 다음 예제와 `StreamReaderEnumerable` LINQ 쿼리에서 합니다.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
