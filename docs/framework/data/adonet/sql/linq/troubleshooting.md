---
title: 문제 해결
ms.date: 03/30/2017
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
ms.openlocfilehash: 6fe4f789ca64c0646b77fdb66b0c6e2b73763293
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43879463"
---
# <a name="troubleshooting"></a>문제 해결
다음은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램에서 발생할 수 있는 문제와 이러한 문제를 방지하거나 문제의 영향을 줄일 수 있는 방법에 대한 설명입니다.  
  
 추가 문제를 해결 [Frequently Asked Questions](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)합니다.  
  
## <a name="unsupported-standard-query-operators"></a>지원되지 않는 표준 쿼리 연산자  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 모든 표준 쿼리 연산자 메서드(예: <xref:System.Linq.Enumerable.ElementAt%2A>)를 지원하지 않습니다. 그 결과 프로젝트를 컴파일할 때 런타임 오류가 발생할 수 있습니다. 자세한 내용은 [표준 쿼리 연산자 변환](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)합니다.  
  
## <a name="memory-issues"></a>메모리 문제  
 쿼리에 메모리 내 컬렉션과 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Table%601>이 포함된 경우 두 컬렉션을 지정한 순서에 따라 쿼리가 메모리 내에서 실행될 수 있습니다. 쿼리를 메모리 내에서 실행해야 할 경우에는 데이터베이스 테이블의 데이터를 가져와야 합니다.  
  
 이 방법은 비효율적이며 메모리와 프로세서를 상당히 많이 사용할 수 있으므로 가능하면 이와 같은 다중 도메인 쿼리를 사용하지 마세요.  
  
## <a name="file-names-and-sqlmetal"></a>파일 이름과 SQLMetal  
 입력 파일 이름을 지정하려면 이름을 명령줄에 입력 파일로 추가합니다. **/conn** 옵션을 사용하여 연결 문자열에 파일 이름을 포함할 수는 없습니다. 자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.  
  
## <a name="class-library-projects"></a>클래스 라이브러리 프로젝트  
 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 프로젝트의 `app.config` 파일에 연결 문자열을 만듭니다. 클래스 라이브러리 프로젝트에는 `app.config` 파일이 사용되지 않으며 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 디자인 타임 파일에 제공되는 연결 문자열을 사용합니다. 따라서 `app.config`에서 값을 변경해도 응용 프로그램에서 연결하는 데이터베이스가 변경되지 않습니다.  
  
## <a name="cascade-delete"></a>하위 삭제  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 하위 삭제 작업을 지원하거나 인식하지 않습니다. 제약 조건이 있는 테이블의 행을 삭제하려면 다음 작업 중 하나를 수행해야 합니다.  
  
-   데이터베이스의 외래 키 제약 조건에 `ON DELETE CASCADE` 규칙을 설정합니다.  
  
-   사용자 고유의 코드를 사용하여 부모 개체를 삭제하는 데 방해가 되는 자식 개체를 먼저 삭제합니다.  
  
 <xref:System.Data.SqlClient.SqlException> 예외가 throw됩니다.  
  
 자세한 내용은 [방법: the 데이터베이스에서 행 삭제](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)합니다.  
  
## <a name="expression-not-queryable"></a>쿼리할 수 없는 식  
 "Expression [expression] 형식의 식은 쿼리할 수 없습니다. 어셈블리 참조가 있는지 확인하십시오." 오류가 나타나면 다음 사항을 확인하십시오.  
  
-   응용 프로그램이 [!INCLUDE[compact_v35_short](../../../../../../includes/compact-v35-short-md.md)]를 대상으로 하는지 여부  
  
-   `System.Core.dll` 및 `System.Data.Linq.dll`에 대한 참조가 있는지 여부  
  
-   해야는 `Imports` (Visual Basic) 또는 `using` (C#) 지시문 <xref:System.Linq> 고 <xref:System.Data.Linq>입니다.  
  
## <a name="duplicatekeyexception"></a>DuplicateKeyException  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 디버깅하는 동안 엔터티의 관계를 이동할 수 있습니다. 이렇게 하면 이러한 항목이 캐시에 들어 오고 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이를 인식합니다. 이 상태에서 <xref:System.Data.Linq.Table%601.Attach%2A>나 <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>을 실행하거나 키가 동일한 여러 행을 생성하는 유사한 메서드를 실행하면 <xref:System.Data.Linq.DuplicateKeyException>이 throw됩니다.  
  
## <a name="string-concatenation-exceptions"></a>문자열 연결 예외  
 `[n]text`와 다른 `[n][var]char`에 매핑된 피연산자는 연결할 수 없습니다. 서로 다른 두 형식 집합에 매핑된 문자열을 연결하면 예외가 throw됩니다. 자세한 내용은 [System.String 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)합니다.  
  
## <a name="skip-and-take-exceptions-in-sql-server-2000"></a>SQL Server 2000의 Skip 및 Take 예외  
 SQL Server 2000 데이터베이스에 대해 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 또는 <xref:System.Linq.Queryable.Take%2A>을 사용할 때는 ID 멤버(<xref:System.Linq.Queryable.Skip%2A>)를 사용해야 합니다. 조인이 아니라 단일 테이블에 대해 쿼리를 실행하거나, 쿼리가 <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> 또는 <xref:System.Linq.Queryable.Union%2A> 작업이어야 하며 쿼리에 <xref:System.Linq.Queryable.Concat%2A> 작업이 포함되면 안 됩니다. 자세한 내용은 "SQL Server 2000 지원" 섹션을 참조 하세요 [표준 쿼리 연산자 변환](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)합니다.  
  
 이 요구 사항은 [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)]에는 적용되지 않습니다.  
  
## <a name="groupby-invalidoperationexception"></a>GroupBy InvalidOperationException  
 <xref:System.Linq.Enumerable.GroupBy%2A>처럼 `boolean` 식을 사용하여 그룹화하는 `group x by (Phone==@phone)` 쿼리에서 열 값이 null이면 이 예외가 throw됩니다. 식이 `boolean`이기 때문에 키가 `boolean` `nullable`이 아니라 `boolean`로 유추됩니다. 변환된 비교 연산의 결과가 null이면 `nullable`에 `boolean` `boolean`을 할당하려고 시도되고 예외가 throw됩니다.  
  
 null을 false로 처리하려는 경우에 이 문제를 해결하려면 다음과 같이 하세요.  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## <a name="oncreated-partial-method"></a>OnCreated() 부분 메서드  
 생성된 `OnCreated()` 메서드는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 원래 값의 복사본을 만들기 위해 생성자를 호출하는 시나리오를 포함하여, 개체 생성자가 호출될 때마다 호출됩니다. 고유한 부분 클래스에 `OnCreated()` 메서드를 구현할 때 이 동작을 고려하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 지원](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 [질문과 대답](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
