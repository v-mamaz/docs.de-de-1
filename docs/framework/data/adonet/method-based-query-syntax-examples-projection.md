---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Projektion (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
ms.openlocfilehash: 0ac595c2fddc6da8eee4d625d418b139a577e4ad
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904464"
---
# <a name="method-based-query-syntax-examples-projection-linq-to-dataset"></a>Beispiele für die methodenbasierte Abfragesyntax: Projektion (LINQ to DataSet)
In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.Select%2A> und <xref:System.Linq.Enumerable.SelectMany%2A> und der methodenbasierten Abfragesyntax ein <xref:System.Data.DataSet> abfragen können.  
  
 Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.  
  
 In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie eine LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="select"></a>Auswählen  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.Select%2A>-Methode verwendet, um die Eigenschaften `Name`, `ProductNumber` und `ListPrice` auf eine Abfolge anonymer Typen zu projizieren.  Im sich dabei ergebenden Typ wird außerdem die `ListPrice`-Eigenschaft in `Price` umbenannt.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="selectmany"></a>SelectMany  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, bei denen `TotalDue` kleiner als 500.00 ist.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, bei denen die Bestellung am 1. Oktober 2002 oder später eingegangen ist.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a>Siehe auch
- [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [Beispiele für LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
