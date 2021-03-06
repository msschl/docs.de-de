---
title: 'Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und die Operatoren „is“ und „as“'
description: Erfahren Sie, wie Sie Techniken für den Musterabgleich anwenden, um Variablen sicher in einen anderen Typ umzuwandeln. Sie können sowohl den Musterabgleich als auch die Operatoren „is“ und „as“ verwenden, um Typen sicher umzuwandeln.
ms.date: 09/05/2018
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.openlocfilehash: 4e0eb53a44a6348d0f5154a0a08222da90985864
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149314"
---
# <a name="how-to-safely-cast-by-using-pattern-matching-is-and-as-operators"></a>Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und die Operatoren „is“ und „as“

Da Objekte polymorph sind, ist es möglich, dass eine Variable eines Basisklassentyps einen abgeleiteten [Typ](../programming-guide/types/index.md) enthalten kann. Für den Zugriff auf die Instanzmember des abgeleiteten Typs ist es erforderlich, dass Sie den Wert wieder in den abgeleiteten Typ [umwandeln](../programming-guide/types/casting-and-type-conversions.md). Allerdings entsteht durch eine Umwandlung das Risiko, eine <xref:System.InvalidCastException>-Ausnahme auszulösen. C# stellt [Musterabgleich](../pattern-matching.md)-Anweisungen bereit, die eine Umwandlung unter der Bedingung ausführen, dass sie erfolgreich sein wird. C# bietet außerdem die Operatoren [is](../language-reference/keywords/is.md) und [as](../language-reference/keywords/as.md), um zu testen, ob ein Wert einen bestimmten Typ aufweist.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Im folgenden Code wird der Musterabgleich mit der `is`-Anweisung veranschaulicht. Sie enthält Methoden, die ein Methodenargument testen, um zu ermitteln, ob es einer möglichen Gruppe von abgeleiteten Typen angehört:

[!code-csharp-interactive[Pattern matching is statement](../../../samples/snippets/csharp/how-to/safelycast/patternmatching/Program.cs#PatternMatchingIs)]

Im vorhergehenden Beispiel werden einige Features der Syntax für den Musterabgleich veranschaulicht. Die Anweisungen `if (a is Mammal m)` und `if (o is Mammal m)` kombinieren den Test mit einer Initialisierungszuweisung. Die Zuweisung tritt nur auf, wenn der Test erfolgreich ist. Die Variable `m` befindet sich nur im Bereich der eingebetteten `if`-Anweisung, dem sie zugewiesen wurde. Sie können in der gleichen Methode später nicht auf `m` zugreifen. Probieren Sie dies im interaktiven Fenster aus.

Sie können die gleiche Syntax zum Testen verwenden, wenn ein [Nullable-Typ](../programming-guide/nullable-types/index.md) wie im folgenden Beispielcode über einen Wert verfügt:

[!code-csharp-interactive[Pattern matching with nullable types](../../../samples/snippets/csharp/how-to/safelycast/nullablepatternmatching/Program.cs#PatternMatchingNullable)]

Im vorhergehenden Beispiel werden weitere Features des Musterabgleichs veranschaulicht, die mit Konvertierungen verwendet werden können. Sie können eine Variable für das NULL-Muster prüfen, indem Sie spezifisch nach dem `null`-Wert sehen. Wenn der Laufzeitwert der Variable `null` ist, gibt eine `is`-Anweisung, die nach einem Typ prüft, immer `false` zurück. Die `is`-Anweisung für den Musterabgleich lässt keinen Nullable-Typ für den Wert zu, z.B. `int?` oder `Nullable<int>`, jedoch können Sie nach jedem anderen Werttyp prüfen.

Im vorhergehenden Beispiel wird auch veranschaulicht, wie Sie den `is`-Ausdruck für den Musterabgleich in einer `switch`-Anweisung verwenden, in der die Variable einen von vielen verschiedenen Typen aufweisen kann.

Wenn Sie testen möchten, ob eine Variable einen bestimmten Typ aufweist, Sie aber keine neue Variable zuweisen möchten, können Sie die Operatoren `is` und `as` für Verweistypen und Nullable-Typen verwenden. Im folgenden Code wird veranschaulicht, wie Sie die Anweisungen `is` und `as` verwenden, die Teil der C#-Sprache waren, bevor der Musterabgleich eingeführt wurde, um zu überprüfen, ob eine Variable einen bestimmten Typ aufweist:

[!code-csharp-interactive[testing variable types with the is and as statements](../../../samples/snippets/csharp/how-to/safelycast/asandis/Program.cs#IsAndAs)]

Wie Sie durch Vergleichen dieses Codes mit dem Code für den Musterabgleich sehen können, stellt die Syntax für den Musterabgleich robustere Features bereit, indem der Test und die Zuweisung in einer einzelnen Anweisung kombiniert werden. Verwenden Sie nach Möglichkeit die Syntax für den Musterabgleich.

Sie können diese Beispiele ausprobieren, indem Sie sich den Code in unserem [GitHub-Repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/safelycast) ansehen. Alternativ dazu können Sie die Beispiele [als ZIP-Datei](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/safelycast.zip) herunterladen.
