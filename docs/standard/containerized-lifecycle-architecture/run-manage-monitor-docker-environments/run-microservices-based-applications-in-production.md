---
title: Ausführen von zusammengesetzten und auf Microservices basierende Anwendungen in produktionsumgebungen
description: Lernen Sie die wesentlichen Komponenten bei containerbasierte Anwendungen in der Produktion ausführen kennen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 52cf273194bff10192b06d236bda7c1cbea1abd8
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835212"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Ausführen von zusammengesetzten und auf Microservices basierende Anwendungen in produktionsumgebungen

Aus mehreren microservices bestehende Anwendungen müssen in der Orchestrator-Cluster, um die Komplexität der Bereitstellung und Umsetzung aus Sicht eines IT bereitgestellt werden. Ohne ein orchestratorcluster würde es schwierig sein, bereitstellen und skalieren Sie eine komplexe Microservices-Anwendung.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Einführung in orchestratoren, Planer und Container-Clustern

Weiter oben in diesem e-Book, *Cluster* und *Zeitplanungsmodule* wurden als Teil der Diskussion auf Softwarearchitektur und-Entwicklung eingeführt. Kubernetes und Service Fabric sind Beispiele für die Docker-Cluster. Sowohl diese orchestratoren können als Teil der Infrastruktur von Microsoft Azure-Kubernetes-Dienst ausführen.

Wenn Anwendungen über mehrere Hostsysteme hinweg horizontal sind, wird die Möglichkeit zum Verwalten von jedem Hostsystem und abstrahieren die Komplexität der zugrunde liegenden Plattform attraktiv. Das ist genau das, was orchestratoren und Planer bereitstellen. Werfen wir einen kurzen Blick auf die sie hier:

- **Planer.** "Planung" bezieht sich auf die Fähigkeit, ein Administrator eine Dienstdatei auf einem Hostsystem zu laden, die wie einen bestimmten Container ausgeführt wird. Starten Container in einem Docker-Cluster ist wie das Planen bekannt sein. Obwohl planen, die mit dem bestimmten Laden der Definition des Diensts in gewisser Hinsicht allgemeineren bezieht sich dienen Zeitplanungsmodule Hooks für Host in der Init-System zum Verwalten von Diensten in beliebige benötigte Kapazität.

   Ein clusterplaner ist, mehrere Ziele: die Ressourcen des Clusters effizient zu verwenden, arbeiten mit benutzerdefinierten platzierungseinschränkungen, Planen Anwendungen schnell nicht im Status "Ausstehend", lassen müssen ein Maß an "faire", wird auf Fehler, robuste und immer verfügbar sein.

- **Orchestratoren**. Plattformen erweitern Life-Cycle Management-Funktionen für komplexe, mit mehreren Containern Workloads, die auf einem Cluster mit Hosts bereitgestellt werden. Durch das abstrahieren die Hostinfrastruktur, Benutzern orchestrierungstools eine Möglichkeit, den gesamten Cluster als ein Bereitstellungsziel aus einzelnen zu behandeln.

   Der Prozess der Orchestrierung umfasst Tools und eine Plattform, die alle Aspekte der Verwaltung von Anwendungen von anfängliche Platzierung oder Bereitstellung pro Container automatisiert werden kann; zu anderen Hosts je nach Zustand oder die Leistung des Hosts Container verschieben versionsverwaltung und parallele Updates und Funktionen, die Skalierung und das Failover unterstützen die Systemüberwachung; und vieles mehr.

   Orchestrierung ist ein weitgefasster Begriff, der auf den Container zu planen, Clusterverwaltung und möglicherweise die Bereitstellung von weitere Hosts verweist.

Die Funktionen von orchestratoren und Planer sind komplex, entwickeln und Erstellen von Grund auf neu, daher in der Regel würde Orchestrierung Lösungen von Anbietern verwenden möchten.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](manage-production-docker-environments.md)
