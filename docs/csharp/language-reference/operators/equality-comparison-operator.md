---
title: ==-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: c6f93be4d422fe42787e36f5b86e2cccbfc645b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239013"
---
# <a name="-operator-c-reference"></a>==-Operator (C#-Referenz)
Für vordefinierte Werttypen gibt der Gleichheitsoperator (`==`) TRUE zurück, wenn die Werte der Operanden gleich sind, andernfalls `false`. Für andere Verweistypen als [string](../../../csharp/language-reference/keywords/string.md) gibt `==` `true` zurück, wenn beide Operanden auf dasselbe Objekt verweisen. Für den `string`-Typ vergleicht `==` die Werte der Zeichenfolgen.  
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Werttypen können den Operator `==` überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)). Dies können auch benutzerdefinierte Verweistypen, obwohl `==` sich standardmäßig für vordefinierte und benutzerdefinierte Verweistypen wie oben beschrieben verhält. Wenn `==` überladen ist, muss [!=](../../../csharp/language-reference/operators/not-equal-operator.md) auch überladen werden. Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
