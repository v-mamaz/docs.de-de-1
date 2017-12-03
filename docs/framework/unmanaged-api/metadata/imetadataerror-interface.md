---
title: IMetaDataError-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError
helpviewer_keywords: IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ae90221a1b305fdf09ae9583e720a2092289362
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="d7be6-102">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7be6-102">IMetaDataError Interface</span></span>
<span data-ttu-id="d7be6-103">Stellt einen Rückrufmechanismus zur Meldung von Fehlern beim Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="d7be6-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7be6-104">Die `IMetaDataError` -Schnittstelle muss vom Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7be6-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7be6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d7be6-105">Methods</span></span>  
  
|<span data-ttu-id="d7be6-106">Methode</span><span class="sxs-lookup"><span data-stu-id="d7be6-106">Method</span></span>|<span data-ttu-id="d7be6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7be6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7be6-108">OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="d7be6-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="d7be6-109">Stellt eine Benachrichtigung von Fehlern, die auftreten, während das Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="d7be6-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7be6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7be6-110">Requirements</span></span>  
 <span data-ttu-id="d7be6-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7be6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7be6-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7be6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7be6-113">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d7be6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7be6-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7be6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7be6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7be6-115">See Also</span></span>  
 [<span data-ttu-id="d7be6-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d7be6-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)