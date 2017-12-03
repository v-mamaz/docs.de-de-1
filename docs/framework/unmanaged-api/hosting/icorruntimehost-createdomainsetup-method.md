---
title: ICorRuntimeHost::CreateDomainSetup-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomainSetup
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca09788ea403e2a60d6de0cb6834fdc90261b770
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="c87e2-102">ICorRuntimeHost::CreateDomainSetup-Methode</span><span class="sxs-lookup"><span data-stu-id="c87e2-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="c87e2-103">Ruft ein Schnittstellenzeiger, der geben IAppDomainSetup auf eine <xref:System.AppDomainSetup?displayProperty=nameWithType> Instanz.</span><span class="sxs-lookup"><span data-stu-id="c87e2-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="c87e2-104">`IAppDomainSetup`Stellt Methoden zum Konfigurieren der Aspekte einer Anwendungsdomäne vor Erstellung.</span><span class="sxs-lookup"><span data-stu-id="c87e2-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c87e2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c87e2-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c87e2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c87e2-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="c87e2-107">[out] Einen Schnittstellenzeiger auf eine <xref:System.AppDomainSetup?displayProperty=nameWithType> Instanz.</span><span class="sxs-lookup"><span data-stu-id="c87e2-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="c87e2-108">Dieser Parameter wird als typisiert `IUnknown`, sodass Aufrufer in der Regel aufrufen sollte `QueryInterface` für diesen Zeiger, erhalten einen Schnittstellenzeiger vom Typ `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="c87e2-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c87e2-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c87e2-109">Return Value</span></span>  
  
|<span data-ttu-id="c87e2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c87e2-110">HRESULT</span></span>|<span data-ttu-id="c87e2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c87e2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c87e2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c87e2-112">S_OK</span></span>|<span data-ttu-id="c87e2-113">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c87e2-113">The operation was successful.</span></span>|  
|<span data-ttu-id="c87e2-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c87e2-114">S_FALSE</span></span>|<span data-ttu-id="c87e2-115">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c87e2-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c87e2-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c87e2-116">E_FAIL</span></span>|<span data-ttu-id="c87e2-117">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c87e2-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c87e2-118">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c87e2-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c87e2-119">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c87e2-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c87e2-120">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="c87e2-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c87e2-121">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c87e2-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c87e2-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c87e2-122">Remarks</span></span>  
 <span data-ttu-id="c87e2-123">Der von dieser Methode zurückgegebene Zeiger wird in der Regel als Parameter an übergeben der [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c87e2-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c87e2-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c87e2-124">Requirements</span></span>  
 <span data-ttu-id="c87e2-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c87e2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c87e2-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c87e2-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c87e2-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c87e2-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c87e2-128">**.NET Framework-Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c87e2-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87e2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c87e2-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [<span data-ttu-id="c87e2-130">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c87e2-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)