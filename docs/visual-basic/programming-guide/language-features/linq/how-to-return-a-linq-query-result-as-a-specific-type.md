---
title: "How to: Return a LINQ Query Result as a Specific Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [LINQ in Visual Basic], specific type returned"
  - "projection [LINQ in Visual Basic]"
  - "anonymous types [Visual Basic]"
  - "querying databases [LINQ]"
  - "queries [LINQ in Visual Basic], how-to topics"
  - "query samples [Visual Basic]"
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Return a LINQ Query Result as a Specific Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

LINQ\(통합 언어 쿼리\)를 사용하면 손쉽게 데이터베이스 정보에 액세스하고 쿼리를 실행할 수 있습니다.  기본적으로 LINQ 쿼리는 개체 목록을 익명 형식으로 반환합니다.  `Select` 절을 사용하여 쿼리에서 특정 형식의 목록을 반환하도록 지정할 수도 있습니다.  
  
 다음 예제에서는 SQL Server 데이터베이스에 대해 쿼리를 수행하고 결과를 특정 명명된 형식으로 예상하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.  자세한 내용은 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 및 [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md)을 참조하십시오.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.  개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트에서 다운로드할 수 있습니다.  자세한 내용은 [샘플 데이터베이스 다운로드](../Topic/Downloading%20Sample%20Databases.md)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### 데이터베이스에 대한 연결을 만들려면  
  
1.  Visual Studio의 **보기** 메뉴에서 **서버 탐색기**\/**데이터베이스 탐색기**를 클릭하여 **서버 탐색기**\/**데이터베이스 탐색기**를 엽니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 **데이터 연결**을 마우스 오른쪽 단추로 클릭한 다음 **연결 추가**를 클릭합니다.  
  
3.  Northwind 샘플 데이터베이스에 대한 유효한 연결을 지정합니다.  
  
### LINQ to SQL 파일이 포함된 프로젝트를 추가하려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  Visual Basic **Windows Forms 응용 프로그램**을 프로젝트 형식으로 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  **LINQ to SQL 클래스** 항목 템플릿을 선택합니다.  
  
3.  파일 이름을 `northwind.dbml`로 지정합니다.  **추가**를 클릭합니다.  northwind.dbml 파일에 대한 O\/R 디자이너\(개체 관계형 디자이너\)가 열립니다.  
  
### 쿼리할 테이블을 O\/R 디자이너에 추가하려면  
  
1.  **서버 탐색기**\/**데이터베이스 탐색기**에서 Northwind 데이터베이스에 대한 연결을 확장합니다.  **테이블** 폴더를 확장합니다.  
  
     O\/R 디자이너를 닫은 경우에는 앞서 추가한 northwind.dbml 파일을 두 번 클릭하여 다시 열 수 있습니다.  
  
2.  Customers 테이블을 클릭하여 디자이너의 왼쪽 창으로 끌어 옵니다.  
  
     디자이너에서 프로젝트에 대한 새 `Customer` 개체를 만듭니다.  쿼리 결과를 `Customer` 형식이나 자신이 만든 형식으로 예상할 수 있습니다.  이 샘플에서는 이후 프로시저에서 새 형식을 만들고 쿼리 결과를 해당 형식으로 예상합니다.  
  
3.  변경 내용을 저장한 다음 디자이너를 닫습니다.  
  
4.  프로젝트를 저장합니다.  
  
### 데이터베이스를 쿼리하여 결과를 표시하는 코드를 추가하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows Form인 Form1로 끌어 옵니다.  
  
2.  Form1을 두 번 클릭하여 Form1 클래스를 수정합니다.  
  
3.  Form1 클래스의 `End Class` 문 뒤에 다음 코드를 추가하고 `CustomerInfo` 형식을 만들어 이 샘플에 대한 쿼리 결과를 저장합니다.  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  O\/R 디자이너에 테이블을 추가한 경우 디자이너는 <xref:System.Data.Linq.DataContext> 개체를 프로젝트에 추가한 것입니다.  이 개체에는 해당 테이블에 액세스하고 각 테이블에 대한 개별 개체와 컬렉션에 액세스하기 위해 가져야 하는 코드가 포함됩니다.  프로젝트에 대한 <xref:System.Data.Linq.DataContext> 개체의 이름은 .dbml 파일 이름을 기반으로 지정됩니다.  이 프로젝트에서 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`입니다.  
  
     코드에서 <xref:System.Data.Linq.DataContext>의 인스턴스를 만든 다음 O\/R 디자이너로 지정된 테이블을 쿼리할 수 있습니다.  
  
     Form1 클래스의 `Load` 이벤트에서 다음 코드를 추가하여 데이터 컨텍스트의 속성으로 노출된 테이블을 쿼리합니다.  쿼리의 `Select` 절은 쿼리 결과의 각 항목에 대해 익명 형식 대신 새 `CustomerInfo` 형식을 만듭니다.  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  F5 키를 눌러 프로젝트를 실행하고 결과를 봅니다.  
  
## 참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [DataContext 메서드\(O\/R 디자이너\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)