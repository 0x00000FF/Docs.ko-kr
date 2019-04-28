---
title: Entity SQL 빠른 참조
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785257"
---
# <a name="entity-sql-quick-reference"></a>Entity SQL 빠른 참조
이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 대한 빠른 참조를 제공합니다. 이 항목의 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.  
  
## <a name="literals"></a>리터럴  
  
### <a name="string"></a>문자열  
 유니코드 문자열 리터럴과 유니코드가 아닌 문자열 리터럴이 있습니다. 유니코드 문자열은 명사를 사용 하 여 앞에 있습니다. 예를 들어 `N'hello'`합니다.  
  
 다음은 비유니코드 문자열 리터럴의 예제입니다.  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 출력:  
  
|값|  
|-----------|  
|hello|  
  
### <a name="datetime"></a>DateTime  
 DateTime 리터럴에서는 날짜와 시간 부분 모두 필수 요소입니다. 기본값은 없습니다.  
  
 예제:  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 출력:  
  
|값|  
|-----------|  
|12/25/2006 1:01:00 AM|  
  
### <a name="integer"></a>정수  
 Integer 리터럴은 Int32(123), UInt32(123U), Int64(123L) 및 UInt64(123UL) 형식일 수 있습니다.  
  
 예제:  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 출력:  
  
|값|  
|-----------|  
|1|  
|2|  
|3|  
  
### <a name="other"></a>기타  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 기타 리터럴은 Guid, Binary, Float/Double, Decimal, `null` 등입니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 Null 리터럴은 개념적 모델의 다른 모든 형식과 호환 가능한 것으로 간주됩니다.  
  
## <a name="type-constructors"></a>형식 생성자  
  
### <a name="row"></a>ROW  
 [행](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) 에서처럼, 구조적으로 형식화 된 익명 레코드 값을 생성 합니다. `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 예제:  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 출력:  
  
|ProductID|이름|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### <a name="multiset"></a>MULTISET  
 [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) 와 같은 컬렉션을 생성 합니다.  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 예제:  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 출력:  
  
|ProductID|이름|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring-Panniers, Large|PA-T100|…|  
  
### <a name="object"></a>개체  
 [형식 생성자 라는](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) 와 같은 명명 된 사용자 정의 개체를 생성 `person("abc", 12)`합니다.  
  
 예제:  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 출력:  
  
|SalesOrderDetailID|CarrierTrackingNumber|OrderQty|ProductID|...|  
|------------------------|---------------------------|--------------|---------------|---------|  
|1|4911-403C-98|1|776|...|  
|2|4911-403C-98|3|777|...|  
|...|...|...|...|...|  
  
## <a name="references"></a>참조  
  
### <a name="ref"></a>REF  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) 엔터티 형식 인스턴스에 대 한 참조를 만듭니다. 예를 들어, 다음 쿼리는 주문 엔터티 집합의 개별 주문 엔터티에 대한 참조를 반환합니다.  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 출력:  
  
|값|  
|-----------|  
|1|  
|2|  
|3|  
|...|  
  
 다음 예제에서는 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스합니다. 속성 추출 연산자가 사용되면 해당 참조가 자동으로 역참조됩니다.  
  
 예제:  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 출력:  
  
|값|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="deref"></a>DEREF  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) 역참조 참조 값과의 결과 생성 합니다. 예를 들어, `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` 쿼리는 Orders 엔터티 집합의 개별 Order별로 Order 엔터티를 생성합니다.  
  
 예제:  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 출력:  
  
|값|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="createref-and-key"></a>CREATEREF 및 KEY  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) 키를 전달 하는 참조를 만듭니다. [키](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) 형식 참조가 있는 식의 키 부분을 추출 합니다.  
  
 예제:  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 출력:  
  
|ProductID|  
|---------------|  
|980|  
|365|  
|771|  
|...|  
  
## <a name="functions"></a>함수  
  
### <a name="canonical"></a>정식  
 에 대 한 네임 스페이스 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) Edm은 `Edm.Length("string")`합니다. 정식 함수와 이름이 같은 함수가 포함된 다른 네임스페이스를 가져오지 않는 한, 네임스페이스를 지정할 필요가 없습니다. 두 네임스페이스의 함수가 동일한 경우 사용자는 전체 이름을 지정해야 합니다.  
  
 예제:  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 출력:  
  
|NameLen|  
|-------------|  
|6|  
|6|  
|5|  
  
### <a name="microsoft-provider-specific"></a>Microsoft 공급자 특정  
 [Microsoft 공급자 특정 함수](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) 에 `SqlServer` 네임 스페이스입니다.  
  
 예제:  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 출력:  
  
|EmailLen|  
|--------------|  
|27|  
|27|  
|26|  
  
## <a name="namespaces"></a>네임스페이스  
 [사용 하 여](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) 쿼리 식에 사용 되는 네임 스페이스를 지정 합니다.  
  
 예제:  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 출력:  
  
|값|  
|-----------|  
|aa|  
  
## <a name="paging"></a>페이징  
 페이징 선언 하 여 표현 될 수 있습니다는 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) 및 [제한](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) 하위 절을 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 절.  
  
 예제:  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 출력:  
  
|ID|이름|  
|--------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## <a name="grouping"></a>그룹화  
 [GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) 쿼리에서 반환 된 개체 그룹을 지정 합니다 ([선택](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) 식 배치 됩니다.  
  
 예제:  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 출력:  
  
|name|  
|----------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## <a name="navigation"></a>탐색  
 관계 탐색 연산자를 사용하여 엔터티 간의(시작 End에서 끝 End) 관계를 탐색할 수 있습니다. [NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) 수행으로 정규화 된 관계 유형을 \<네임 스페이스 >.\< 관계 유형 이름 >. 이동 Ref 반환\<T > 경우의 카디널리티를 종료 하는 1입니다. 하는 경우의 카디널리티를 종료 하려면 n, 컬렉션은 < Ref\<T >> 반환 됩니다.  
  
 예제:  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 출력:  
  
|AddressID|  
|---------------|  
|1|  
|2|  
|3|  
|...|  
  
## <a name="select-value-and-select"></a>SELECT VALUE 및 SELECT  
  
### <a name="select-value"></a>SELECT VALUE  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 암시적 행 생성을 건너뛰도록 SELECT VALUE 절을 제공합니다. SELECT VALUE 절에 하나의 항목만 지정할 수 있습니다. 이러한 절은 사용 되는 SELECT 절의 항목 주위에 없는 행 래퍼가 생성 하 고 원하는 모양의 컬렉션이 만들어질 수 있습니다 예를 들어: `SELECT VALUE a`합니다.  
  
 예제:  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 출력:  
  
|이름|  
|----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="select"></a>선택  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 임의의 행을 만드는 행 생성자도 제공합니다. SELECT는 `SELECT a, b, c`와 같이 프로젝션의 요소를 하나 이상 사용하며 필드가 있는 데이터 레코드를 생성합니다.  
  
 예제:  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p 출력:  
  
|이름|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## <a name="case-expression"></a>CASE 식  
 합니다 [사례 식을](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) 결과 결정 하는 부울 식 집합을 계산 합니다.  
  
 예제:  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 출력:  
  
|값|  
|-----------|  
|TRUE|  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
