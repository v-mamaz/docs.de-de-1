---
title: 'Vorgehensweise: Ausrichten von gezeichnetem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: ab97ab713067af26455fa4261bbddaf900ec91b8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725258"
---
# <a name="how-to-align-drawn-text"></a>Vorgehensweise: Ausrichten von gezeichnetem Text
Wenn Sie eine benutzerdefinierte Zeichnung durchführen, sollten Sie häufig gezeichnetem Text in einem Formular oder Steuerelement zu zentrieren. Sie können problemlos mit gezeichneter Text Ausrichten der <xref:System.Drawing.Graphics.DrawString%2A> oder <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden, mit der richtigen Formatierungsobjekt erstellen und Festlegen von Flags für die Kultur spezifische Format.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>So zeichnen Sie zentrierten Text mit GDI + ("DrawString")  
  
1.  Verwenden einer <xref:System.Drawing.StringFormat> mit dem entsprechenden <xref:System.Drawing.Graphics.DrawString%2A> Methode, um zentriert Text anzugeben.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>So zeichnen Sie zentrierten Text mit GDI (DrawText)  
  
1.  Verwenden der <xref:System.Windows.Forms.TextFormatFlags> Enumeration für wrapping als auch vertikal und horizontal zentrieren Text mit der entsprechenden <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die vorherigen Codebeispiele für den Einsatz mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
- [Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten](how-to-construct-font-families-and-fonts.md)
