---
title: '방법: Windows Forms 컨트롤에서 사용자 입력된 이벤트를 처리 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: e4fa03a07e97fe1d860b281b8e5cece0c41d6c27
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56331963"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a>방법: Windows Forms 컨트롤에서 사용자 입력된 이벤트를 처리 합니다.
이 예제에서는 Windows Forms 컨트롤에서 발생할 수 있는 대부분의 키보드, 마우스, 포커스 및 유효성 검사 이벤트를 처리하는 방법을 보여 줍니다. 포커스가 있을 경우 `TextBoxInput`이라는 텍스트 상자가 이벤트를 수신하며, 각 이벤트에 대한 정보가 이벤트 발생 순서대로 `TextBoxOutput`이라는 텍스트 상자에 기록됩니다. 애플리케이션에는 보고할 이벤트를 필터링하는 데 사용할 수 있는 확인란 집합도 포함되어 있습니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- [Windows Forms에 사용자 입력](../../../docs/framework/winforms/user-input-in-windows-forms.md)
