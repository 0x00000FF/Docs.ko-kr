---
title: XSLT 변형을 DataSet에 적용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: 3f066f29b99ade6e92a263110fed8079208567b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151496"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a>XSLT 변형을 DataSet에 적용

**의 WriteXml** 방법을 <xref:System.Data.DataSet> 사용하면 **데이터 집합의** 내용을 XML 데이터로 작성할 수 있습니다. 그런 다음에는 XSLT(XSL transformations)를 사용하여 해당 XML을 다른 형식으로 변환하는 공통적인 작업이 수행됩니다. 그러나 **DataSet을** 와 <xref:System.Xml.XmlDataDocument> 동기화하면 **WriteXml을**사용하여 **DataSet의** 내용을 XML 데이터로 먼저 쓸 필요 없이 **데이터 집합의** 내용에 XSLT 스타일시트를 적용할 수 있습니다.  
  
 다음 예제에서는 **데이터 집합을** 테이블 및 관계로 채우고, **데이터 집합을** **XmlDataDocument와**동기화하고, XSLT 스타일시트를 사용하여 **DataSet의** 일부를 HTML 파일로 씁니다. 다음은 XSLT 스타일시트의 내용입니다.
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 다음 코드는 **데이터 집합을** 채우고 XSLT 스타일 시트를 적용합니다.  
  
> [!NOTE]
> 구속조건을 포함하는 **DataSet에** XSLT 스타일 시트를 적용하는 경우 각 중첩 관계에 대해 의 <xref:System.Data.DataRelation> **중첩** 속성을 **true로** 설정하면 최상의 성능을 얻을 수 있습니다. 그러면 스타일시트 노드 테스트 식에서 쓰는 이전 형제 및 다음 형제와 같이 높은 성능이 필요한 XPath 위치 축을 사용하여 데이터 계층을 탐색하는 대신, 자연스러운 상-하 처리를 구현하는 XSLT 스타일시트를 사용하여 계층을 탐색하고 데이터를 전송할 수 있습니다. 중첩 된 관계에 대한 자세한 내용은 [중첩 데이터 관계](nesting-datarelations.md)를 참조하십시오.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a>참고 항목

- [데이터 세트 및 XmlDataDocument 동기화](dataset-and-xmldatadocument-synchronization.md)
- [ADO.NET 개요](../ado-net-overview.md)
