---
title: Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23fa927dcdb91fb3905f1cbe845450751de91157
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50180074"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult
Typen in .NET Framework- und Klassenbibliotheken von Drittanbietern können Methoden bereitstellen, die einer Anwendung während der Durchführung asynchroner Vorgänge die weitere Ausführung in anderen Threads als dem Hauptanwendungsthread ermöglichen. In den folgenden Abschnitten werden Codebeispiele beschrieben und angegeben, die die verschiedenen Möglichkeiten für den Aufruf asynchroner Methoden mit dem Entwurfsmuster <xref:System.IAsyncResult> veranschaulichen.  
  
-   [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)  
  
-   [Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)  
  
-   [Abrufen des Status eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)  
  
-   [Verwenden eines AsyncCallback-Delegaten zum Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
