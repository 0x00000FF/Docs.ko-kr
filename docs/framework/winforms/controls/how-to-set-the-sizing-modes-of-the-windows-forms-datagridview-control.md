---
title: "방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "데이터 표, 크기 조정 모드 설정"
  - "DataGridView 컨트롤[Windows Forms], 크기 조정 모드"
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정
다음 절차에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 컨트롤의 특정 열에 사용할 수 있는 크기를 사용자 지정하거나 결합하는 몇 가지 일반적인 시나리오를 보여 줍니다.  
  
### 고정 너비 열을 만들려면 다음을 수행합니다.  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>으로 설정하고, <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> 속성을 <xref:System.Windows.Forms.DataGridViewTriState>로 설정하고, <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성을 `true`로 설정하고, <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> 속성을 적절한 값으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### 콘텐츠에 맞게 크기를 조정하는 열을 만들려면 다음을 수행합니다.  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성을 콘텐츠 기반 크기 조정 모드로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### 다양한 크기 및 중요도 값에 대한 채우기 모드 열을 만들려면 다음을 수행합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=fullName> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>로 설정하여 이 값을 재정의하지 않는 모든 열에 대한 크기 조정 코드를 설정합니다.  열의 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성을 평균 콘텐츠 너비에 비례하는 값으로 설정합니다.  중요도 열의 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 속성을 설정하여 부분 콘텐츠 표시를 제공합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## 예제  
 다음 전체 코드 예제에서는 이 항목에 설명된 크기 조정 옵션을 이해하는 데 도움이 될 수 있는 데모 응용 프로그램을 제공합니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 이 데모 응용 프로그램을 사용하려면 다음을 수행합니다.  
  
-   폼 크기를 변경합니다.  <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성 값으로 지정된 비율을 유지하면서 채우기 모드 열에서 어떻게 너비가 변경되는지 관찰합니다.  폼이 너무 작을 때 열의 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>가 어떻게 너비가 변경되지 않도록 방지하는지 관찰합니다.  
  
-   마우스로 열 구분선을 끌어서 열 크기를 변경합니다.  일부 열을 어떻게 크기 조정할 수 없는지, 크기 조정 가능한 열을 어떻게 최소 너비보다 더 작게 설정할 수 있는지 관찰합니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>   
 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=fullName>