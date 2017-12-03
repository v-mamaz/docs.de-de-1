---
title: COR_PRF_GC_REASON-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_REASON
helpviewer_keywords: COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a5797c3e629bc87caf40b187bba47bc1cffbfdf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="96e16-102">COR_PRF_GC_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="96e16-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="96e16-103">Zeigt den Grund, weshalb die Garbage Collection stattfindet.</span><span class="sxs-lookup"><span data-stu-id="96e16-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96e16-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="96e16-105">Member</span><span class="sxs-lookup"><span data-stu-id="96e16-105">Members</span></span>  
  
|<span data-ttu-id="96e16-106">Member</span><span class="sxs-lookup"><span data-stu-id="96e16-106">Member</span></span>|<span data-ttu-id="96e16-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96e16-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="96e16-108">Die Garbagecollection ausgelöst wurde, indem eine <xref:System.GC.Collect%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="96e16-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="96e16-109">Der Grund ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="96e16-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96e16-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96e16-110">Requirements</span></span>  
 <span data-ttu-id="96e16-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96e16-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96e16-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96e16-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96e16-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96e16-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96e16-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e16-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e16-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96e16-115">See Also</span></span>  
 [<span data-ttu-id="96e16-116">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="96e16-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)