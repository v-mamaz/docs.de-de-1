---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: aaf0dd9d6918f2c248942cee3773eee8332adda9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552839"
---
# <a name="binding"></a>Bindung
wmi-Bindung  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Bindungsklasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Bindungsklasse verfügt über die folgenden Eigenschaften.  
  
### <a name="bindingelements"></a>BindingElements  
 Datentyp: BindingElement-array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung der durch die Bindung implementierten Bindungselemente.  
  
### <a name="closetimeout"></a>CloseTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Schließvorgangs bereitgestellt wird.  
  
### <a name="name"></a>name  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name der Bindung.  
  
### <a name="namespace"></a>Namespace  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der XML-Namespace der Bindung.  
  
### <a name="opentimeout"></a>OpenTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Öffnungsvorgangs bereitgestellt wird.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Empfangsvorgangs bereitgestellt wird.  
  
### <a name="scheme"></a>Schema  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das URI-Transportschema, das von den Kanal- und Listener-Factorys verwendet wird, die von der Bindung erstellt werden.  
  
### <a name="sendtimeout"></a>SendTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das für den Abschluss eines Sendevorgangs bereitgestellt wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Channels.Binding>
