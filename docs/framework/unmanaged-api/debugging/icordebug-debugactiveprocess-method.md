---
title: ICorDebug::DebugActiveProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b3869c9f96eee6f0e3066a99a58a154a2f5f2ee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480090"
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess-Methode
Wird der Debugger an einen vorhandenen Prozess angefügt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `id`  
 [in] Die ID des Prozesses, für die der Debugger wird angefügt werden.  
  
 `win32Attach`  
 [in] Boolescher Wert, der festgelegt wird, um `true` Wenn der Debugger sollte sich so wie Win32-Debugger für den Prozess Verhalten und die nicht verwalteten Rückrufe; anderenfalls `false`.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die Adresse ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, an dem der Debugger angefügt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Interop-Debuggen wird auf Win9x und nicht-X86-Plattformen wie z. B. IA-64- und AMD64-basierten Plattformen nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
