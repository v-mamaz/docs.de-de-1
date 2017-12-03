---
title: EnumerateCLRs-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EnumerateCLRs
api_location: dbgshim.dll
api_type: COM
f1_keywords: EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4d4c9502b52f521b9faa8e8d352f0721af68314
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="enumerateclrs-function"></a><span data-ttu-id="9907d-102">EnumerateCLRs-Funktion</span><span class="sxs-lookup"><span data-stu-id="9907d-102">EnumerateCLRs Function</span></span>
<span data-ttu-id="9907d-103">Stellt einen Mechanismus für das Auflisten der CLRs in einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="9907d-103">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9907d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9907d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9907d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9907d-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="9907d-106">[in] Die Prozess-ID des Prozesses aus dem geladene CLRs aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="9907d-106">[in] Process identifier of the process from which loaded CLRs will be enumerated.</span></span>  
  
 `ppHandleArrayOut`  
 <span data-ttu-id="9907d-107">[out] Ein Zeiger auf ein Array mit Ereignishandles, die zum Fortsetzen eines CLR-Starts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9907d-107">[out] Pointer to an array containing event handles that are used to continue a CLR startup.</span></span> <span data-ttu-id="9907d-108">Die Gültigkeit der einzelnen Handle im Array ist nicht garantiert.</span><span class="sxs-lookup"><span data-stu-id="9907d-108">Each handle in the array is not guaranteed to be valid.</span></span> <span data-ttu-id="9907d-109">Wenn das Handle gültig ist, wird es als Ereignis zur Startfortsetzung für die entsprechende Common Language Runtime im gleichen Index von `ppStringArrayOut` verwendet.</span><span class="sxs-lookup"><span data-stu-id="9907d-109">If valid, the handle is to be used as the continue-startup event for the corresponding runtime located in the same index of `ppStringArrayOut`.</span></span>  
  
 `ppStringArrayOut`  
 <span data-ttu-id="9907d-110">[out] Ein Zeiger auf ein Array von Zeichenfolgen, die vollständige Pfade zu CLRs angeben, die in den Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9907d-110">[out] Pointer to an array of strings that specify full paths to CLRs loaded in the process.</span></span>  
  
 `pdwArrayLengthOut`  
 <span data-ttu-id="9907d-111">[out] Ein Zeiger auf ein DWORD, das die Länge des gleichlangen `ppHandleArrayOut` und `pdwArrayLengthOut` enthält.</span><span class="sxs-lookup"><span data-stu-id="9907d-111">[out] Pointer to a DWORD that contains the length of the equally sized `ppHandleArrayOut` and `pdwArrayLengthOut`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9907d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9907d-112">Return Value</span></span>  
 <span data-ttu-id="9907d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9907d-113">S_OK</span></span>  
 <span data-ttu-id="9907d-114">Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9907d-114">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="9907d-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9907d-115">E_INVALIDARG</span></span>  
 <span data-ttu-id="9907d-116">Entweder ist `ppHandleArrayOut` oder `ppStringArrayOut` Null, oder `pdwArrayLengthOut` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="9907d-116">Either `ppHandleArrayOut` or `ppStringArrayOut` is null, or `pdwArrayLengthOut` is null.</span></span>  
  
 <span data-ttu-id="9907d-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9907d-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9907d-118">Die Funktion kann nicht genug Speicher für die Handle- und Pfadarrays reservieren.</span><span class="sxs-lookup"><span data-stu-id="9907d-118">The function is unable to allocate enough memory for the handle and path arrays.</span></span>  
  
 <span data-ttu-id="9907d-119">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="9907d-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9907d-120">Geladene CLRs können nicht aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="9907d-120">Unable to enumerate loaded CLRs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9907d-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9907d-121">Remarks</span></span>  
 <span data-ttu-id="9907d-122">Für einen Zielprozess, der durch `debuggeePID` identifiziert wird, gibt die Funktion ein Array von Pfaden, `ppStringArrayOut`, an im Prozess geladene CLRs, ein Array von Ereignishandles, `ppHandleArrayOut`, das möglicherweise ein Ereignis zur Startfortsetzung für die CLR in demselben Index enthält, und die Größe der Arrays zurück, `pdwArrayLengthOut`, die die Anzahl der geladenen CLRs angibt.</span><span class="sxs-lookup"><span data-stu-id="9907d-122">For a target process that is identified by `debuggeePID`, the function returns an array of paths, `ppStringArrayOut`, to CLRs loaded in the process; an array of event handles, `ppHandleArrayOut`, which may contain a continue-startup event for the CLR at the same index; and the size of the arrays, `pdwArrayLengthOut`, which specifies the number of CLRs that are loaded.</span></span>  
  
 <span data-ttu-id="9907d-123">Unter dem Windows-Betriebssystem wird `debuggeePID` einem Betriebssystem-Prozessbezeichner zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9907d-123">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="9907d-124">Der Arbeitsspeicher für `ppHandleArrayOut` und `ppStringArrayOut` wird von dieser Funktion zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9907d-124">The memory for `ppHandleArrayOut` and `ppStringArrayOut` are allocated by this function.</span></span> <span data-ttu-id="9907d-125">Um den belegten Arbeitsspeicher freizugeben, rufen Sie [CloseCLREnumeration-Funktion](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md).</span><span class="sxs-lookup"><span data-stu-id="9907d-125">To free the memory allocated, you must call [CloseCLREnumeration Function](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md).</span></span>  
  
 <span data-ttu-id="9907d-126">Diese Funktion kann mit beiden auf null festgelegten Arrayparametern aufgerufen werden, um die Anzahl der CLRs im Zielprozess zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="9907d-126">This function can be called with both array parameters set to null in order to return the count of CLRs in the target process.</span></span> <span data-ttu-id="9907d-127">Aus dieser Anzahl kann ein Aufrufer die Größe des Puffers ableiten, der erstellt wird: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span><span class="sxs-lookup"><span data-stu-id="9907d-127">From this count, a caller can infer the size of the buffer that will be created: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9907d-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9907d-128">Requirements</span></span>  
 <span data-ttu-id="9907d-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9907d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9907d-130">**Header:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="9907d-130">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9907d-131">**Bibliothek:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="9907d-131">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9907d-132">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9907d-132">**.NET Framework Versions:** 3.5 SP1</span></span>