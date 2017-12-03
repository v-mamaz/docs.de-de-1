---
title: "&lt;Entfernen Sie&gt; -Element für &lt;\"configSections\"&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e6dfd1ac56070f55f30bd4bd093e1185486da295
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="a6176-102">\<Entfernen Sie >-Element für \<ConfigSections ></span><span class="sxs-lookup"><span data-stu-id="a6176-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="a6176-103">Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="a6176-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="a6176-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a6176-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="a6176-105">&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="a6176-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="a6176-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Entfernen >**</span><span class="sxs-lookup"><span data-stu-id="a6176-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a6176-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6176-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="a6176-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="a6176-108">Attribute</span></span>

|           | <span data-ttu-id="a6176-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6176-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="a6176-110">**name**</span><span class="sxs-lookup"><span data-stu-id="a6176-110">**name**</span></span>  | <span data-ttu-id="a6176-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a6176-111">Required attribute.</span></span><br><br><span data-ttu-id="a6176-112">Gibt den Namen des Abschnitts oder Abschnittsgruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a6176-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="a6176-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="a6176-113">Parent element</span></span>

|     | <span data-ttu-id="a6176-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6176-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a6176-115">**\<ConfigSections >** Element</span><span class="sxs-lookup"><span data-stu-id="a6176-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="a6176-116">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="a6176-116">Contains configuration section and namespace declarations.</span></span> |

# <a name="child-elements"></a><span data-ttu-id="a6176-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a6176-117">Child elements</span></span>

<span data-ttu-id="a6176-118">Keine</span><span class="sxs-lookup"><span data-stu-id="a6176-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="a6176-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6176-119">Remarks</span></span>

<span data-ttu-id="a6176-120">Können Sie die  **\<entfernen >** Element Abschnitte und Abschnittsgruppen aus der Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="a6176-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="a6176-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6176-121">Example</span></span>

<span data-ttu-id="a6176-122">Das folgende Beispiel zeigt, wie Sie die  **\<entfernen >** Element in einer Anwendungskonfigurationsdatei zum Entfernen eines Bereichs, die zuvor in der Computerkonfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="a6176-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="a6176-123">Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<SampleSection >**:</span><span class="sxs-lookup"><span data-stu-id="a6176-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="a6176-124">Der folgende Code für eine Anwendungskonfigurationsdatei entfernt die  **\<SampleSection >** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a6176-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="a6176-125">Nach dem entfernen die Anwendung kann nicht die Einstellungen in abrufen  **\<SampleSection >**.</span><span class="sxs-lookup"><span data-stu-id="a6176-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="a6176-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a6176-126">Configuration file</span></span>

<span data-ttu-id="a6176-127">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="a6176-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6176-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6176-128">See also</span></span>

[<span data-ttu-id="a6176-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6176-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)