---
title: 'Vorgehensweise: Das Bild angezeigt, die von einer Windows Forms-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 93bc7970ce7c287273f8bd7ff50b07c6658e2a08
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644923"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Vorgehensweise: Das Bild angezeigt, die von einer Windows Forms-Steuerelement
Mehrerer Windows Forms-Steuerelemente können Bilder anzeigen. Diese Images können Symbole, die Erläuterung des Zwecks des Steuerelements, z. B. ein Diskettensymbol auf eine Schaltfläche, werden die **speichern** Befehl. Alternativ können die Symbole Hintergrundbilder, um die Kontrolle zu haben, die Darstellung und das gewünschte Verhalten sein.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Das von einem Steuerelement angezeigte Bild festlegen  
  
1.  Legen Sie die `Image` oder `BackgroundImage` Eigenschaft, um ein Objekt des Typs <xref:System.Drawing.Image>. In der Regel Laden Sie das Image aus einer Datei mithilfe der <xref:System.Drawing.Image.FromFile%2A> Methode.  
  
     Das folgende Codebeispiel zeigt der Pfad festgelegt, für der Speicherort des Images ist der **eigene Bilder** Ordner. Die meisten Computer, die das Windows-Betriebssystem ausgeführt wird, werden dieses Verzeichnis enthalten. Dies ermöglicht auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Das folgende Codebeispiel ist erforderlich, dass Sie bereits ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement hinzugefügt.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
