---
title: 'Vorgehensweise: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: af18cf3fc155148816690bdd16baa3a2a5515eee
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368518"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Vorgehensweise: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft
Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Sie können Folgendes zum Abrufen der <xref:System.Windows.Data.Binding> Objekt:  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.  
  
 Alternativ können Sie erhalten die <xref:System.Windows.Data.BindingExpression> und rufen Sie anschließend den Wert des der <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> Eigenschaft.  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](https://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Wenn die Bindung ist eine <xref:System.Windows.Data.MultiBinding>, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>. Ist dies ein <xref:System.Windows.Data.PriorityBinding>, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>. Falls Sie unsicher sind, ob die Eigenschaft gebunden ist mit einer <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>, oder ein <xref:System.Windows.Data.PriorityBinding>, können Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## <a name="see-also"></a>Siehe auch
- [Erstellen einer Bindung in Code](how-to-create-a-binding-in-code.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
