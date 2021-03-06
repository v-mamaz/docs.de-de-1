---
title: ColorConvertedBitmap-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: e51a39b6516d88f53b54f8ab7c1c0d1ad4c025e1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363877"
---
# <a name="colorconvertedbitmap-markup-extension"></a>ColorConvertedBitmap-Markuperweiterung
Bietet eine Möglichkeit, eine Bitmapquelle angeben, die nicht über ein eingebettetes Profil verfügt. Farbkontexte / Profile angegebenen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], wie die Bildquelle [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`imageSource`|Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der für Bitmap.|  
|`sourceIIC`|Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] von der Quelle-Profilkonfiguration.|  
|`destinationIIC`|Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] von der Ziel-Profilkonfiguration|  
  
## <a name="remarks"></a>Hinweise  
 Diese Markuperweiterung soll z. B. Geben Sie eine zusammengehörige Gruppe von Eigenschaftswerten Bildquelle <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. `ColorConvertedBitmap` (oder `ColorConvertedBitmapExtension`) kann nicht im Eigenschaftenelement-Syntax, verwendet werden, da die Werte nur als Werte auf den ursprünglichen Konstruktor festgelegt werden können, die Zeichenfolge folgen den Erweiterungsbezeichner.  
  
 `ColorConvertedBitmap` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md)
