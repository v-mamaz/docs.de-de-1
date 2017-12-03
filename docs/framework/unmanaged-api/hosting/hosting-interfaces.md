---
title: Hostingschnittstellen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3cad92c204fa10f72d7a9a61460f1234206cb39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-interfaces"></a><span data-ttu-id="019d8-102">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="019d8-102">Hosting Interfaces</span></span>
<span data-ttu-id="019d8-103">Dieser Abschnitt beschreibt die Schnittstellen, die nicht verwaltete Hosts können Sie die common Language Runtime (CLR) in ihre Anwendungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="019d8-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="019d8-104">Die .NET Framework Version 2.0 Hostschnittstellen der .NET Framework Version 1.0 und 1.1-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="019d8-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="019d8-105">Es gibt bedeutende Unterschiede zwischen den beiden Sätzen von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="019d8-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="019d8-106">Mischen sie kann unerwartetes Verhalten verursachen und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="019d8-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="019d8-107">.NET Framework-Versionen 3.0 und 3.5 verwenden die .NET Framework Version 2.0-Hostingschnittstellen und Hostingfunktionen führen.</span><span class="sxs-lookup"><span data-stu-id="019d8-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="019d8-108">Die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Hostschnittstellen das .NET Framework 2.0-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="019d8-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="019d8-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="019d8-109">In This Section</span></span>  
 [<span data-ttu-id="019d8-110">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="019d8-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="019d8-111">Beschreibt die hosting-Schnittstellen in den .NET Framework-Versionen 1.0 und 1.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="019d8-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="019d8-112">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="019d8-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="019d8-113">Beschreibt die hosting-Schnittstellen in .NET Framework, Version 2.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="019d8-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="019d8-114">CLR-Hostingschnittstellen hinzugefügt in .NET Framework 4 und 4.5</span><span class="sxs-lookup"><span data-stu-id="019d8-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="019d8-115">Beschreibt die Hostingschnittstellen eingeführt, die der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="019d8-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="019d8-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="019d8-116">Related Sections</span></span>  
 [<span data-ttu-id="019d8-117">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="019d8-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="019d8-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="019d8-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="019d8-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="019d8-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="019d8-120">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="019d8-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="019d8-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="019d8-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 [<span data-ttu-id="019d8-122">Laufzeithosts</span><span class="sxs-lookup"><span data-stu-id="019d8-122">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)