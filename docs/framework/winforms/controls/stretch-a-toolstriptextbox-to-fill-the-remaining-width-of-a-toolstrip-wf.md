---
title: 'Vorgehensweise: Strecken einer ToolStripTextBox zum Ausfüllen der verbleibenden Breite eines ToolStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 7a557a3d278c2b6d8d083b2ebf8c8129bc498afa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702762"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Vorgehensweise: Strecken einer ToolStripTextBox zum Ausfüllen der verbleibenden Breite eines ToolStrip (Windows Forms)
Beim Festlegen der <xref:System.Windows.Forms.ToolStrip.Stretch%2A> Eigenschaft eine <xref:System.Windows.Forms.ToolStrip> die Steuerung an `true`, das Steuerelement ausfüllt seinem Container von a bis z und ändert, wenn die Größe des Containers ändert. In dieser Konfiguration Umständen ist es nützlich, um ein Element im Steuerelement, z. B. stretch eine <xref:System.Windows.Forms.ToolStripTextBox>, um den verfügbaren Platz ausfüllen und Größe ändern, wenn die Größe des Steuerelements ändert. Dieses Strecken eignet, z. B. Wenn Sie Aussehen und Verhalten der-Adressleiste in Microsoft® Internet Explorer ähnelt erreichen möchten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel stellt eine Klasse, die von abgeleiteten bereit <xref:System.Windows.Forms.ToolStripTextBox> namens `ToolStripSpringTextBox`. Diese Klasse überschreibt die <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> Methode zum Berechnen der verfügbaren Breite des übergeordneten Elements <xref:System.Windows.Forms.ToolStrip> steuern, nachdem die kombinierte Breite aller anderen Elemente subtrahiert wurde. Dieses Codebeispiel bietet auch eine <xref:System.Windows.Forms.Form> Klasse und ein `Program` Klasse, um das neue Verhalten zeigen.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Vorgehensweise: Interaktive Verwendung der Spring-Eigenschaft in StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
