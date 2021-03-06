---
title: 'Vorgehensweise: Festlegen der Höhe eines Fensters von einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: e25bc3cf2f5de01177f79f671390bac39875d079
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Vorgehensweise: Festlegen der Höhe eines Fensters von einer Seite
In diesem Beispiel wird veranschaulicht, wie der Höhe des Fensters aus einem <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.Page> kann durch Festlegen der Höhe der entsprechende Hostfenster festgelegt <xref:System.Windows.Controls.Page.WindowHeight%2A>. Diese Eigenschaft ermöglicht die <xref:System.Windows.Controls.Page> keine explizite Kenntnisse in den Typ des Fensters aufweisen, die diese hostet.  
  
> [!NOTE]
>  Die Höhe eines Fensters mithilfe festzulegende <xref:System.Windows.Controls.Page.WindowHeight%2A>ein <xref:System.Windows.Controls.Page> muss das untergeordnete Element eines Fensters.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
