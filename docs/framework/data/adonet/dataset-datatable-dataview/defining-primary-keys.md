---
title: 定義主索引鍵
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 21d63aa33e20019f8392b81fb69881296a52cb26
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757576"
---
# <a name="defining-primary-keys"></a>定義主索引鍵
資料庫資料表通常會有資料行或資料行群組，可唯一識別資料表的每個資料列。 這個識別欄位或資料行群組又稱為主索引鍵。  
  
 當您識別單一<xref:System.Data.DataColumn>為<xref:System.Data.DataTable.PrimaryKey%2A>的<xref:System.Data.DataTable>，資料表會自動設定<xref:System.Data.DataColumn.AllowDBNull%2A>屬性的資料行**false**和<xref:System.Data.DataColumn.Unique%2A>屬性**true**。 多重資料行主索引鍵，只能**AllowDBNull**屬性會自動設定為**false**。  
  
 **PrimaryKey**屬性<xref:System.Data.DataTable>接收其值為一或多個陣列**DataColumn**物件，如下列範例所示。 第一個範例定義單一資料行為主索引鍵。  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 下列範例定義兩個資料行作為主索引鍵。  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Data.DataTable>  
 [DataTable 結構描述定義](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
