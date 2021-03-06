---
title: Verzögertes im Vergleich zu unmittelbarem Laden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
ms.openlocfilehash: 5955d7361658c825c120e62e531b72d402a12650
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360349"
---
# <a name="deferred-versus-immediate-loading"></a>Verzögertes im Vergleich zu unmittelbarem Laden
Wenn Sie eine Abfrage für ein Objekt durchführen, wird nur das angeforderte Objekt abgerufen. Die *verwandte* Objekte werden nicht automatisch zum gleichen Zeitpunkt abgerufen. (Weitere Informationen finden Sie unter [Beziehungsübergreifendes](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) Für Sie ist nicht erkennbar, dass verwandte Objekte nicht bereits geladen sind, da der Versuch, auf diese Objekte zuzugreifen, eine Abfrage erzeugt, die diese Objekte abruft.  
  
 Sie möchten z. B. für eine bestimmte Gruppe von Bestellungen abzufragen, und klicken Sie dann nur gelegentlich eine e-Mail-Benachrichtigung an bestimmte Kunden senden. Sie müssen nicht notwendigerweise zunächst alle Kundendaten zu jeder Bestellung abrufen. Sie können mithilfe von verzögertem Laden weitere Informationen erst dann abrufen, wenn Sie diese benötigen. Betrachten Sie das folgende Beispiel:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 Das Gegenteil könnte auch zutreffen. Möglicherweise verwenden Sie eine Anwendung, die Kunden- und Bestelldaten gleichzeitig anzeigen muss. Sie wissen, dass Sie beide Datensätze benötigen. Sie wissen, dass die Anwendung Bestellinformationen für jeden Kunden benötigt, sobald Sie die Ergebnisse abrufen. Sie möchten nicht einzelne Abfragen zu den Bestellungen jedes einzelnen Kunden übergeben. Sie möchten stattdessen die Bestelldaten zusammen mit den Kunden abrufen.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 Sie können auch Kunden und Bestellungen in einer Abfrage zusammenfassen, indem Sie diese produktübergreifend gestalten und alle erforderlichen Daten in Form einer großen Projektion abrufen. Diese Ergebnisse sind jedoch keine Entitäten. (Weitere Informationen finden Sie unter [das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)). Entitäten sind Objekte, die Sie verändern können. Bei diesen Ergebnissen handelt es sich jedoch um Projektionen, die nicht verändert und erhalten werden können. Darüber hinaus würden Sie eine Menge redundanter Daten abrufen, da sich die Kunden bei jeder Bestellung in der optimierten gemeinsamen Abfrage wiederholen.  
  
 Sie benötigen stattdessen eine Möglichkeit, verwandte Objekte zur gleichen Zeit abzurufen. Dieser Satz ist ein isolierter Bereich eines Graphen, sodass Sie niemals mehr oder weniger Daten als benötigt abrufen. Zu diesem Zweck [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet <xref:System.Data.Linq.DataLoadOptions> für sofortige Laden einer Region Ihres Objektmodells. Die Methoden umfassen:  
  
-   Die <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>-Methode zum sofortigen Laden von Daten zum Hauptziel.  
  
-   Die <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode zum Filtern abgerufener Objekte nach einer bestimmten Beziehung.  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
