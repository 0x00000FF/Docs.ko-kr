---
title: '방법: 백그라운드 작업을 사용하는 폼 구현'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd9951929fb030e12c32e8470e5ea433645c4d77
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a>방법: 백그라운드 작업을 사용하는 폼 구현
다음 예제 프로그램은 피보나치 숫자를 계산하는 폼을 만듭니다. 계산은 사용자 인터페이스 스레드와 별개인 스레드에서 실행되므로 계산이 진행될 때 사용자 인터페이스가 지연 없이 계속 실행됩니다.  
  
 Visual Studio에서는 이 작업이 광범위하게 지원됩니다.  
  
 또한 [연습: 백그라운드 작업을 사용하는 양식 구현](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\))을 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  또한 [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
> [!CAUTION]
>  모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다. 다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [이벤트 기반 비동기 패턴 개요](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)
