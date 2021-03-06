---
title: 'Gewusst wie: Anzeigen der PrintDialog-Komponente'
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: d8765187522f8becf24b519434b7c170c1c755b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532186"
---
# <a name="how-to-display-the-printdialog-component"></a>Gewusst wie: Anzeigen der PrintDialog-Komponente
Die <xref:System.Windows.Forms.PrintDialog> Komponente ist der standard Windows-Dialogfeld "Drucken"-Feld, das viele Ihrer Benutzer vertraut werden. Da Ihre Benutzer sofort mit der sie vertraut sind, wäre es auch hilfreich, für die Verwendung der <xref:System.Windows.Forms.PrintDialog> Komponente.  
  
### <a name="to-display-the-printdialog-component"></a>So zeigen Sie die PrintDialog-Komponente an  
  
-   Rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> Methode innerhalb der Code Ihrer Anwendung.  
  
     Sobald die Komponente angezeigt wird, können die Benutzer damit interagieren und die Eigenschaften für den Druckauftrag einstellen. Diese gespeichert sind, der <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` Klasse (und die <xref:System.Drawing.Printing.PageSettings> Klasse, wenn der Benutzer zugreift der [PageSetupDialog-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) über die <xref:System.Windows.Forms.PrintDialog> Komponente) mit dem Druckauftrag verknüpft sind. Dann können Sie Aufrufe an die von ihnen eingestellten Eigenschaften durchführen, um die spezifischen Merkmale des Druckauftrags anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [Gewusst wie: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [PrintDialog-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)
