---
title: Abfrageausdruckssyntax für Standardabfrageoperatoren (C#)
ms.date: 07/20/2015
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
ms.openlocfilehash: 46923b34fce08a9ddb8152e51a5308aa7d557ca3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514460"
---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a>Abfrageausdruckssyntax für Standardabfrageoperatoren (C#)
Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über eine dedizierte Schlüsselwortsyntax von C#, wodurch sie als Teil eines *Abfrageausdrucks* aufgerufen werden können. Mit einem Abfrageausdruck kann eine Abfrage besser lesbar ausgedrückt werden als mit dessen *methodenbasierter* Entsprechung. Die Abfrageausdrucksklauseln werden bei der Kompilierung in Aufrufe der Abfragemethoden übersetzt.  
  
## <a name="query-expression-syntax-table"></a>Tabelle: Abfrageausdruckssyntax  
 In der folgenden Tabelle finden Sie eine Liste von Standardabfrageoperatoren, die über äquivalente Abfrageausdrucksklauseln verfügen.  
  
|Methode|C#-Abfrageausdruckssyntax|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|Verwenden Sie eine explizit typisierte Bereichsvariable, z.B.:<br /><br /> `from int i in numbers`<br /><br /> (Weitere Informationen finden Sie unter [from-Klausel](../../../../csharp/language-reference/keywords/from-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> - oder - <br /><br /> `group … by … into …`<br /><br /> (Weitere Informationen finden Sie unter [group-Klausel](../../../../csharp/language-reference/keywords/group-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> (Weitere Informationen finden Sie unter [join-Klausel](../../../../csharp/language-reference/keywords/join-clause.md).)|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> (Weitere Informationen finden Sie unter [join-Klausel](../../../../csharp/language-reference/keywords/join-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> (Weitere Informationen finden Sie unter [orderby-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> (Weitere Informationen finden Sie unter [orderby-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> (Weitere Informationen finden Sie unter [select-Klausel](../../../../csharp/language-reference/keywords/select-clause.md).)|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Mehrere `from`-Klauseln.<br /><br /> (Weitere Informationen finden Sie unter [from-Klausel](../../../../csharp/language-reference/keywords/from-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> (Weitere Informationen finden Sie unter [orderby-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> (Weitere Informationen finden Sie unter [orderby-Klausel](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> (Weitere Informationen finden Sie unter [where-Klausel](../../../../csharp/language-reference/keywords/where-clause.md).)|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable>  
- <xref:System.Linq.Queryable>  
- [Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [Classification of Standard Query Operators by Manner of Execution (C#) (Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten (C#))](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
