---
title: "방법: LINQ를 사용하여 쿼리 결과 필터링(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d2e93d9b4518482b22c78d10d31c4035bdf587e
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 쿼리 결과 필터링(Visual Basic)
통합 언어 쿼리 (LINQ)을 사용 하면 쉽게 데이터베이스 정보에 액세스 하 고 쿼리를 실행할 수 있습니다.  
  
 SQL Server 데이터베이스에 대 한 쿼리를 수행 하 고 특정 값으로 사용 하 여 결과 필터링 하는 새 응용 프로그램을 만드는 방법을 보여 주는 다음 예제는 `Where` 절. 자세한 내용은 참조 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다. 개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우에서 다운로드할 수 있습니다는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다. 자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 연결을 만들려면  
  
1.  Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.  
  
2.  마우스 오른쪽 단추로 클릭 **데이터 연결** 에 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 고 **연결 추가**합니다.  
  
3.  Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다. Visual basic **Windows Forms 응용 프로그램** 프로젝트 형식으로.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. 선택 된 **LINQ to SQL 클래스** 항목 템플릿을 합니다.  
  
3.  파일 이름을 `northwind.dbml`로 지정합니다. **추가**를 클릭합니다. 개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>O/R 디자이너를 쿼리 하는 테이블을 추가 하려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다. 확장 된 **테이블** 폴더입니다.  
  
     O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일이 두 번 클릭 하 여 다시 열 수 있습니다.  
  
2.  Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다. Orders 테이블을 클릭 하 고 디자이너의 왼쪽된 창으로 끕니다.  
  
     디자이너가 새 만들어 `Customer` 및 `Order` 프로젝트에 대 한 개체입니다. 고 해당 데이터베이스 디자이너 자동으로 테이블 간의 관계를 검색 자식 관련된 개체에 대 한 속성을 만듭니다. 예를 들어, IntelliSense는 표시 됩니다는 `Customer` 개체에는 `Orders` 해당 고객에 게 관련 된 모든 주문에 대 한 속성입니다.  
  
3.  변경 내용을 저장 하 고 디자이너를 닫습니다.  
  
4.  프로젝트를 저장합니다.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>데이터베이스를 쿼리하고 결과 표시 하는 코드를 추가 하려면  
  
1.  **도구 상자**를 끌어는 <xref:System.Windows.Forms.DataGridView> Form1 프로젝트에 대 한 기본 Windows Form 컨트롤입니다.  
  
2.  Form1 코드를 추가 하려면 두 번 클릭 하 고 `Load` 폼의 이벤트입니다.  
  
3.  O/R 디자이너에 테이블을 추가 하는 경우에 디자이너 추가 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체입니다. 이 개체는 개별 개체와 각 테이블에 대 한 컬렉션 외에도 해당 테이블에 액세스 해야 하는 코드를 포함 합니다. <xref:System.Data.Linq.DataContext> .dbml 파일의 이름에 따라 프로젝트에 대 한 개체입니다. 이 프로젝트는 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`합니다.  
  
     인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext> 코드와 쿼리에서 O/R 디자이너에서 지정 된 테이블입니다.  
  
     다음 코드를 추가 하 고 `Load` 데이터 컨텍스트 클래스의 속성으로 노출 되는 테이블을 쿼리 하는 이벤트입니다. 쿼리 결과 필터링 하 고에 있는 고객만 반환 `London`합니다.  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.  
  
5.  다음은 몇 가지 다른 필터를 테스트해 볼 수 있습니다.  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [DataContext 메서드 (O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
