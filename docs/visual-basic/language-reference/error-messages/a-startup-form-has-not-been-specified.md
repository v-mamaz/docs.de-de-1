---
title: Es wurde kein Startformular angegeben.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: f05358f76829768d8ff5c4ac85b5134f35254126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627212"
---
# <a name="a-startup-form-has-not-been-specified"></a>Es wurde kein Startformular angegeben.
Die Anwendung verwendet die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> -Klasse jedoch nicht das Startformular angegeben.  
  
 Dies kann auftreten, wenn die **Anwendungsframework aktivieren** im Projekt-Designer das Kontrollkästchen aktiviert ist, aber die **Startformular** nicht angegeben ist. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie ein Startobjekt, für die Anwendung.  
  
     Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2.  Überschreiben der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Methode zum Festlegen der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> Eigenschaft, um das Startformular.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
