---
title: "방법: Windows Forms ListView 컨트롤의 Tile 보기 사용 | Microsoft Docs"
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
  - "ListView 컨트롤[Windows Forms], Tile 보기"
  - "Tile 보기 기능"
  - "바둑판식 배열"
  - "Windows Forms, 컨트롤"
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 방법: Windows Forms ListView 컨트롤의 Tile 보기 사용
<xref:System.Windows.Forms.ListView> 컨트롤의 바둑판식 뷰 기능을 통해 그래픽 정보와 텍스트 정보 간의 시각적 균형을 제공할 수 있습니다.  바둑판식 뷰에서 항목에 대해 표시되는 텍스트 정보는 세부 정보 뷰에 대해 정의된 열 정보와 같습니다.  바둑판식 뷰는 <xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 또는 삽입 표시 기능과 함께 작동합니다.  
  
 다음 이미지와 같이 바둑판식 뷰는 32 x 32 픽셀 아이콘과 여러 줄의 텍스트를 사용합니다.  
  
 ![ListView 컨트롤의 Tile 보기](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
바둑판식 뷰 아이콘 및 텍스트  
  
 바둑판식 뷰를 사용하도록 설정하려면 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View>로 설정합니다.  <xref:System.Windows.Forms.ListView.TileSize%2A> 속성을 설정하여 타일 크기를 조정하고, <xref:System.Windows.Forms.ListView.Columns%2A> 컬렉션을 조정하여 타일에 표시되는 텍스트 줄 수를 조정할 수 있습니다.  
  
> [!NOTE]
>  바둑판식 뷰는 응용 프로그램이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다.  이전 운영 체제에서는 바둑판식 뷰와 관련된 코드가 아무 효과도 없으며, <xref:System.Windows.Forms.ListView> 컨트롤이 큰 아이콘 보기에 표시됩니다.  자세한 내용은 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=fullName>을 참조하세요.  
  
### 프로그래밍 방식으로 바둑판식 뷰를 설정하려면  
  
1.  <xref:System.Windows.Forms.ListView> 컨트롤의 <xref:System.Windows.Forms.View> 열거형을 사용합니다.  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## 예제  
 다음 전체 코드 예제에서는 타일이 3줄의 텍스트를 표시하도록 수정된 바둑판식 뷰를 보여 줍니다.  줄 바꿈을 방지하기 위해 타일 크기가 조정되었습니다.  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
-   실행 파일과 동일한 디렉터리에 있는 book.ico로 명명된 아이콘 파일  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.TileSize%2A>   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ko-kr/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)