---
title: 'Vorgehensweise: Navigieren Sie zu einer Seite'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa4d0881d7dcdb2c56c66c5617652ec1a2cbc374
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="27bf8-102">Vorgehensweise: Navigieren Sie zu einer Seite</span><span class="sxs-lookup"><span data-stu-id="27bf8-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="27bf8-103">Dieses Beispiel veranschaulicht mehrere Möglichkeiten, in dem eine Seite kann navigiert werden, aus, einer <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="27bf8-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27bf8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27bf8-104">Example</span></span>  
 <span data-ttu-id="27bf8-105">Es ist möglich, dass eine <xref:System.Windows.Navigation.NavigationWindow> zum Navigieren zu einer Seite mit einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="27bf8-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
-   <span data-ttu-id="27bf8-106">Die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="27bf8-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
-   <span data-ttu-id="27bf8-107">Die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="27bf8-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]<span data-ttu-id="27bf8-108">kann entweder relativ oder absolut sein.</span><span class="sxs-lookup"><span data-stu-id="27bf8-108"> can be either relative or absolute.</span></span> <span data-ttu-id="27bf8-109">Weitere Informationen finden Sie unter [Paket-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="27bf8-109">For more information, see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27bf8-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27bf8-110">See Also</span></span>  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.NavigationService>