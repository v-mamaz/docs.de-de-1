---
title: 'Vorgehensweise: Fortsetzen eines Windows-Diensts (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: 86c2414fd6ad9c32a37339c553ec80c98426f78a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612709"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Vorgehensweise: Fortsetzen eines Windows-Diensts (Visual Basic)
In diesem Beispiel wird die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet, um den IIS-Verwaltungsdienst auf dem lokalen Computer fortzusetzen.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Er befindet sich in der Codeausschnittauswahl unter **Windows-Betriebssystem > Windows-Dienste**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Projektverweis auf „System.serviceprocess.dll“.  
  
-   Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Standardeinstellung für die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft der <xref:System.ServiceProcess.ServiceController>-Klasse ist der lokale Computer. Ändern Sie zum Verweisen auf die Windows-Dienste auf einem anderen Computer die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft in den Namen des entsprechenden Computers.  
  
 Die <xref:System.ServiceProcess.ServiceController.Continue%2A>-Methode für einen Dienst kann erst aufgerufen werden, wenn der Status des Dienstcontrollers <xref:System.ServiceProcess.ServiceControllerStatus.Paused> lautet.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Dienst kann nicht fortgesetzt werden. (<xref:System.InvalidOperationException>)  
  
-   Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die Steuerung von Diensten auf dem Computer kann mithilfe der <xref:System.ServiceProcess.ServiceControllerPermissionAccess>-Enumeration eingeschränkt werden, um Berechtigungen in der <xref:System.ServiceProcess.ServiceControllerPermission>-Klasse festzulegen.  
  
 Der Zugriff auf Dienstinformationen kann mithilfe der <xref:System.Security.Permissions.PermissionState>-Enumeration eingeschränkt werden, um Berechtigungen in der <xref:System.Security.Permissions.SecurityPermission>-Klasse festzulegen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
