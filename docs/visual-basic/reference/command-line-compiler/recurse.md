---
title: -Recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 1edb648ec574c0052b7b8314f4ada710c8b0fe01
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183333"
---
# <a name="-recurse"></a>-Recurse
Kompiliert Quellcode-Dateien in allen untergeordneten Verzeichnissen im angegebenen Verzeichnis oder dem Projektverzeichnis.  
  
## <a name="syntax"></a>Syntax  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumente  
 `dir`  
 Dies ist optional. Das Verzeichnis, in dem die Suche beginnen soll. Wenn nicht angegeben ist, beginnt die Suche, im Projektverzeichnis.  
  
 `file`  
 Erforderlich. Die Datei(en), nach der oder denen gesucht werden soll. Platzhalterzeichen sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne mit `-recurse`. Wenn kein Dateiname für die Ausgabe angegeben wird, basiert der Compiler den Ausgabedateinamen auf der ersten Eingabedatei verarbeitet. Dies ist in der Regel die erste Datei in der Liste der Dateien, die kompiliert, wenn alphabetisch angezeigt. Aus diesem Grund ist es am besten, geben Sie eine Ausgabe mit der `-out` Option.  
  
> [!NOTE]
>  Die `-recurse` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert, alle Visual Basic-Dateien im aktuellen Verzeichnis.  
  
```console
vbc *.vb  
```  
  
 Der folgende Befehl kompiliert, alle Visual Basic-Dateien in die `Test\ABC` Verzeichnis und allen Verzeichnisse darunter, und generiert dann `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
