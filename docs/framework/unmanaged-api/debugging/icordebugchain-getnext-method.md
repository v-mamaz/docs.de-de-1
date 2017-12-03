---
title: ICorDebugChain::GetNext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetNext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1955d503b612ce4b3a6c4eaaae2003b652f38fd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="f8554-102">ICorDebugChain::GetNext-Methode</span><span class="sxs-lookup"><span data-stu-id="f8554-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="f8554-103">Ruft die nächste Kette von Frames für den Thread an.</span><span class="sxs-lookup"><span data-stu-id="f8554-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8554-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8554-104">Syntax</span></span>  
  
```  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8554-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8554-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="f8554-106">[out] Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die nächste Kette von Frames für den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="f8554-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="f8554-107">Wenn diese Kette die letzte Kette ist `ppChain` ist null.</span><span class="sxs-lookup"><span data-stu-id="f8554-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8554-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8554-108">Requirements</span></span>  
 <span data-ttu-id="f8554-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8554-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8554-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8554-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8554-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8554-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8554-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8554-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>