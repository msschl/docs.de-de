---
title: get – C#-Referenz
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: e3cd4779b4f865c4c9bb46d4f25819c863de8bc2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240033"
---
# <a name="get-c-reference"></a>get (C#-Referenz)

Das Schlüsselwort `get` definiert eine *Accessor*methode in einer Eigenschaft oder einem Indexer, die den Eigenschaftswert oder das Indexer-Element zurückgibt. Weitere Informationen finden Sie unter [Properties (Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers (Indexer)](../../../csharp/programming-guide/indexers/index.md).  
  
Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert. Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
Der `get`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt). Ab C# 7.0 können Sie die `get`-Zugriffsmethode als Ausdruckskörpermember implementieren. Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen. Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft implementiert. 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)
- [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)
