---
title: ICorDebugThread2::GetActiveFunctions-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetActiveFunctions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1f7f416a5441b788394e93a98d274d02fa2ec2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="ee0a7-102">ICorDebugThread2::GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="ee0a7-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="ee0a7-103">Ruft Informationen über die aktive Funktion in den einzelnen Frames dieses Threads ab.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee0a7-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee0a7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee0a7-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="ee0a7-106">[in] Die Größe des `pFunctions`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="ee0a7-107">[out] Ein Zeiger auf die Anzahl der zurückgegebenen Objekte die `pFunctions` Array.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="ee0a7-108">Die Anzahl der zurückgegebenen Objekte wird die Anzahl der verwalteten Frames auf dem Stapel gleich sein.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="ee0a7-109">[in, out] Ein Array von COR_ACTIVE_FUNCTION-Objekten, von denen jede Informationen über die aktiven Funktionen im Rahmen dieses Threads enthält.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="ee0a7-110">Das erste Element wird für den Endframe und usw. bis zurück zum Stammverzeichnis des Stapels verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee0a7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee0a7-111">Remarks</span></span>  
 <span data-ttu-id="ee0a7-112">Wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt nur die Anzahl der Funktionen, die im Stapel befinden.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="ee0a7-113">D. h. wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt einen Wert nur in `pcFunctions`.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="ee0a7-114">Die `GetActiveFunctions` Methode dient nur zur Optimierung über die gleichen Informationen abrufen, von Frames in eine stapelüberwachung und enthält nur die Frames, die ein Objekt ICorDebugILFrame dafür in das vollständige stapelüberwachung müssten.</span><span class="sxs-lookup"><span data-stu-id="ee0a7-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee0a7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee0a7-115">Requirements</span></span>  
 <span data-ttu-id="ee0a7-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee0a7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee0a7-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee0a7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee0a7-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee0a7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee0a7-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee0a7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>