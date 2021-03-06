---
title: 'Vorgehensweise: Auflisten installierter Encoder'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 492930b7d8a47db478c8fa0f282cb5f491e144ac
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708456"
---
# <a name="how-to-list-installed-encoders"></a>Vorgehensweise: Auflisten installierter Encoder
Möglicherweise möchten die Liste auf einem Computer verfügbaren Bildencoder um festzustellen, ob Ihre Anwendung auf ein bestimmtes Bildformat Datei speichern kann. Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> statische Methoden, damit Sie bestimmen können, welche Encoder verfügbar sind. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel gibt die Liste der installierten Encoder und der zugehörigen Eigenschaftswerte enthält.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Eine Windows Forms-Anwendung  
  
-   Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Auflisten installierter Decoder](how-to-list-installed-decoders.md)
- [Verwenden von Bildencodern und -decodern in Managed GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)
