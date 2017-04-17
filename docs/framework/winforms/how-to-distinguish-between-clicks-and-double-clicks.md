---
title: "방법: 클릭과 두 번 클릭 간 구별 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "마우스 클릭, 한 번 클릭과 두 번 클릭 비교"
  - "마우스, 클릭"
  - "마우스, 두 번 클릭"
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 클릭과 두 번 클릭 간 구별
일반적으로 단일 *클릭*은 UI\(사용자 인터페이스\) 동작을 시작하고 *두 번 클릭*은 동작을 확장합니다.  예를 들어 한 번 클릭은 대개 항목을 선택하고 두 번 클릭은 선택된 항목을 편집합니다.  그러나 Windows Forms 클릭 이벤트는 한 번 클릭과 두 번 클릭이 호환되지 않는 동작을 수행하는 시나리오에는 쉽게 적용되지 않습니다. <xref:System.Windows.Forms.Control.Click> 또는 <xref:System.Windows.Forms.Control.MouseClick> 이벤트에 연결된 동작이 <xref:System.Windows.Forms.Control.DoubleClick> 또는 <xref:System.Windows.Forms.Control.MouseDoubleClick> 이벤트에 연결된 동작 앞에 수행되기 때문입니다.  이 항목에서는 이 문제에 대한 두 가지 솔루션을 보여 줍니다.  한 솔루션은 두 번 클릭 이벤트를 처리하고 클릭 이벤트 처리 시 작업을 롤백하는 것입니다.  드물지만 <xref:System.Windows.Forms.Control.MouseDown> 이벤트를 처리하고 <xref:System.Windows.Forms.SystemInformation> 클래스의 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 및 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 속성을 사용하여 클릭 및 두 번 클릭 동작을 시뮬레이션해야 할 수 있습니다.  클릭 사이의 시간을 측정하고, <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 값에 도달하기 전에 두 번째 클릭이 발생하고 클릭이 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>에서 정의된 사각형 내에 있으면 두 번 클릭 동작을 수행하고, 그러지 않으면 클릭 동작을 수행합니다.  
  
### 클릭 동작을 롤백하려면 다음을 수행합니다.  
  
-   작업하고 있는 컨트롤에 표준 두 번 클릭 동작이 있는지 확인합니다.  그러지 않으면 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드로 컨트롤을 사용하도록 설정합니다.  두 번 클릭 이벤트를 처리하고 두 번 클릭 동작과 클릭 동작을 롤백합니다.  다음 코드 예제에서는 두 번 클릭이 사용되는 사용자 지정 단추를 만드는 방법과 두 번 클릭 이벤트 처리 코드에서 클릭 동작을 롤백하는 방법을 보여 줍니다.  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### MouseDown 이벤트에서 클릭을 구분하려면 다음을 수행합니다.  
  
-   <xref:System.Windows.Forms.Control.MouseDown> 이벤트를 처리하고 적절한 <xref:System.Windows.Forms.SystemInformation> 속성 및 <xref:System.Windows.Forms.Timer> 구성 요소를 사용하여 클릭 사이의 위치 및 시간 차이를 결정합니다.  클릭 또는 두 번 클릭이 수행되는지에 따라 적절한 동작을 수행합니다.  다음 코드 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## 코드 컴파일  
 이러한 예제에는 다음이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]용으로 이들 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이들 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)