---
title: CorGCReferenceType-Enumeration
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ac36f6d0dba92742ea7a7acfadc194930ccd74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516442"
---
# <a name="corgcreferencetype-enumeration"></a>CorGCReferenceType-Enumeration
Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>Member  
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|`CorHandleStrong`|Ein Handle für einen starken Verweis von der Objekthandletabelle.|  
|`CorHandleStrongPinning`|Ein Handle auf ein angehefteter starker Verweis von der objekthandletabelle.|  
|`CorHandleWeakShort`|Ein Handle zu einem schwachen Verweis von der objekthandletabelle.|  
|`CorHandleWeakRefCount`|Ein Handle zu einem schwachen Verweis gezähltes Objekt von der objekthandletabelle.|  
|`CorHandleStrongRefCount`|Ein Handle auf ein Objekt mit verweiszählung von der objekthandletabelle.|  
|`CorHandleStrongDependent`|Ein Handle auf ein abhängiges Objekt von der objekthandletabelle.|  
|`CorHandleStrongAsyncPinned`|Ein asynchrones angeheftetes Objekt von der Objekthandletabelle.|  
|`CorHandleStrongSizedByref`|Ein starkes Handle, das eine ungefähre Größe des kollektiven Abschlusses aller Objekte und Objektstämme zur Garbage Collection-Zeit enthält.|  
|`CorReferenceStack`|Ein Verweis von den verwalteten Stapel.|  
|`CorReferenceFinalizer`|Ein Verweis von der Finalizer-Warteschlange.|  
|CorHandleStrongOnly|Nur zuverlässige Verweise aus der Handletabelle zurück. Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.|  
|`CorHandleWeakOnly`|Nur schwache Verweise aus der Handletabelle zurück. Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.|  
|`CorHandleAll`|Alle Verweise aus der Handletabelle zurück. Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CorGCReferenceType` Enumeration wird folgendermaßen verwendet:  
  
-   Als Wert für die `type` Feld der [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Struktur gibt die Quelle der einen Verweis oder einen Handle an.  
  
-   Als die `types` Argument für die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) -Methode, die die Arten von Handles in der Enumeration eingeschlossen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
