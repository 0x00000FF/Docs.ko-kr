---
title: "PrintDocument 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f052283b743d5f1a7ed9d2bb6576390e5343dcae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="printdocument-component-overview-windows-forms"></a>PrintDocument 구성 요소 개요(Windows Forms)
Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 구성 요소는 인쇄 대상 및 Windows 기반 응용 프로그램 내에서 문서를 인쇄하는 기능을 설명하는 속성을 설정하는 데 사용됩니다. 모든 문서 인쇄 측면의 제어에 포함되도록 [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) 구성 요소와 함께 사용할 수 있습니다.  
  
## <a name="working-with-the-printdocument-component"></a>PrintDocument 구성 요소 작업  
 두 가지와 관련 된 주요 시나리오는 <xref:System.Drawing.Printing.PrintDocument> 요소 됩니다:  
  
-   개별 텍스트 파일 인쇄 등의 간단한 인쇄 작업. 이러한 경우에 추가 된 <xref:System.Drawing.Printing.PrintDocument> 을 Windows Form에 구성 요소 다음에 파일을 인쇄 하는 프로그래밍 논리를 추가 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기입니다. 프로그래밍 논리 끝나야는 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드는 문서를 인쇄 합니다. 이 메서드는 전송는 <xref:System.Drawing.Graphics> 에 포함 된 개체는 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 의 속성은 <xref:System.Drawing.Printing.PrintPageEventArgs> 프린터로 클래스입니다. 사용 하 여 텍스트 문서를 인쇄 하는 방법을 보여 주는 예제는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 참조 [하는 방법: Windows Forms에서 다중 페이지 텍스트 파일을 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)합니다.  
  
-   작성한 인쇄 논리를 다시 사용하려는 상황과 같은 좀 더 복잡한 인쇄 작업. 이 경우 새 구성 요소에서 파생는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소와 재정의 (참조 [재정의](~/docs/visual-basic/language-reference/modifiers/overrides.md) Visual basic의 경우 또는 [재정의](~/docs/csharp/language-reference/keywords/override.md) C#)는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트입니다.  
  
 폼에 추가 될 때의 <xref:System.Drawing.Printing.PrintDocument> 구성 요소는 Windows Forms 디자이너 아래쪽에서 트레이에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [PrintDocument 구성 요소](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
