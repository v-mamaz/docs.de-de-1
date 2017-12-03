---
title: ICorDebugInternalFrame2::GetFrameAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2.GetFrameAddress Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ee867afe99fc5d2f2eb27bb1e6888aef8341d71
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="5167d-102">ICorDebugInternalFrame2::GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="5167d-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="5167d-103">Gibt die Stapeladresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="5167d-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5167d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5167d-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5167d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5167d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="5167d-106">[out] Zeiger auf die `CORDB_ADDRESS` für den internen Frame.</span><span class="sxs-lookup"><span data-stu-id="5167d-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5167d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5167d-107">Return Value</span></span>  
 <span data-ttu-id="5167d-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5167d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5167d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5167d-109">HRESULT</span></span>|<span data-ttu-id="5167d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5167d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5167d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5167d-111">S_OK</span></span>|<span data-ttu-id="5167d-112">Die Adresse des internen Frames wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5167d-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="5167d-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5167d-113">E_FAIL</span></span>|<span data-ttu-id="5167d-114">Die Adresse des internen Frames konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5167d-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="5167d-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5167d-115">E_INVALIDARG</span></span>|<span data-ttu-id="5167d-116">`pAddress` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="5167d-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5167d-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5167d-117">Remarks</span></span>  
 <span data-ttu-id="5167d-118">Der zurückgegebene Wert in `pAddress` können verwendet werden, um die Position des internen Frames relativ zu anderen Frames auf dem Stapel zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="5167d-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="5167d-119">Auch auf IA-64-basierten Computern internen Frames auf dem Stapel nur aktiv ist und keine entsprechenden Zeiger auf einen Sicherungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="5167d-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5167d-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5167d-120">Requirements</span></span>  
 <span data-ttu-id="5167d-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5167d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5167d-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5167d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5167d-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5167d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5167d-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5167d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5167d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5167d-125">See Also</span></span>  
 [<span data-ttu-id="5167d-126">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5167d-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="5167d-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5167d-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5167d-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5167d-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)