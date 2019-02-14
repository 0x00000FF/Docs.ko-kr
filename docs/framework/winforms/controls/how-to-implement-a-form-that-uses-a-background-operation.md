---
title: '방법: 백그라운드 작업을 사용 하는 폼 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 9ace37b1c79ff2e5cd06fce08557dc6cdf2fcc11
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261310"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a>방법: 백그라운드 작업을 사용 하는 폼 구현
다음 예제 프로그램은 피보나치 숫자를 계산하는 폼을 만듭니다. 계산은 사용자 인터페이스 스레드와 별개인 스레드에서 실행되므로 계산이 진행될 때 사용자 인터페이스가 지연 없이 계속 실행됩니다.  
  
 Visual Studio에서는 이 작업이 광범위하게 지원됩니다.  
  
 또한 참조 [연습: 백그라운드 작업을 사용 하는 폼 구현](walkthrough-implementing-a-form-that-uses-a-background-operation.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
> [!CAUTION]
>  모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다. 다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [이벤트 기반 비동기 패턴 개요](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)
