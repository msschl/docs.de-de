---
title: "\"SqlTypes\" und \"DataSet\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: fe00e669449d40320a2038697976423db83ade5b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511546"
---
# <a name="sqltypes-and-the-dataset"></a>"SqlTypes" und "DataSet"
Mit ADO.NET 2.0 wurde eine erweiterte Typunterstützung für das `DataSet` durch den <xref:System.Data.SqlTypes>-Namespace eingeführt. Die Typen in <xref:System.Data.SqlTypes> stellen Datentypen mit derselben Semantik und Präzision wie die Datentypen in einer SQL Server-Datenbank bereit. Für jeden Datentyp in <xref:System.Data.SqlTypes> gibt es einen äquivalenten Datentyp in SQL Server mit derselben zugrunde liegenden Datendarstellung.  
  
 Die direkte Verwendung von <xref:System.Data.SqlTypes> in einem <xref:System.Data.DataSet> beim Arbeiten mit SQL Server-Datentypen hat mehrere Vorteile. <xref:System.Data.SqlTypes> unterstützt die gleiche Semantik wie systemeigene SQL Server-Datentypen. Bei Angabe eines <xref:System.Data.SqlTypes> in der Definition eines <xref:System.Data.DataColumn>-Objekts wird der Verlust an Genauigkeit ausgeglichen, die auftreten kann, wenn Dezimaldatentypen oder numerische Datentypen zu einem Datentyp der Common Language Runtime (CLR) konvertiert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Data.DataTable>-Objekt erstellt. Dabei werden explizit die <xref:System.Data.DataColumn>-Datentypen definiert, wobei anstelle von CLR-Typen <xref:System.Data.SqlTypes> verwendet werden. Der Code füllt die <xref:System.Data.DataTable> mit Daten aus der Sales.SalesOrderDetail-Tabelle in der SQL Server-AdventureWorks-Datenbank. In der Ausgabe im Konsolenfenster werden der Datentyp der einzelnen Spalten und die von SQL Server abgerufenen Werte angezeigt.  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [Konfigurieren von Parametern und Parameterdatentypen](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
