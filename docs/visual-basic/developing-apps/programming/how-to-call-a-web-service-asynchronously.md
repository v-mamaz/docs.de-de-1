---
title: 'Vorgehensweise: Asynchrones Aufrufen eines Webdiensts (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: 01d2fad6be94f23457ba37cbb15521765e0bea17
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376203"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a>Vorgehensweise: Asynchrones Aufrufen eines Webdiensts (Visual Basic)

Dieses Beispiel hängt einen Handler an das asynchrone Handlerereignis eines Webdiensts an, sodass dieses das Ergebnis eines asynchronen Methodenaufrufs abrufen kann. Dieses Beispiel verwendet den Webdienst DemoTemperatureService unter `http://www.xmethods.net`.

Wenn Sie im Projekt in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio auf einen Webdienst verweisen, wird dieser dem `My.WebServices`-Objekt hinzugefügt und die IDE generiert eine Client-Proxyklasse für den Zugriff auf einen festgelegten Webdienst.

Mit der Proxyklasse ist es möglich, die Webdienstmethoden synchron aufzurufen, während die Anwendung darauf wartet, dass die Funktion abgeschlossen wird. Außerdem erstellt das Proxy weitere Member zur asynchronen Unterstütztung der Methode. Für jede Webdienstfunktion, *NameOfWebServiceFunction*, erstellt das Proxy eine *NameOfWebServiceFunction*`Async`-Unterroutine, ein *NameOfWebServiceFunction*`Completed`-Ereignis und eine *NameOfWebServiceFunction*`CompletedEventArgs`-Klasse. Dieses Beispiel demonstriert, wie Sie die asynchronen Member für den Zugriff auf die `getTemp`-Funktion des Webdiensts DemoTemperatureService verwenden.

> [!NOTE]
> Dieser Code funktioniert nicht in Webanwendungen, denn ASP.NET unterstützt nicht das Objekt `My.WebServices`.

### <a name="to-call-a-web-service-asynchronously"></a>Asynchroner Aufruf eines Webdiensts

1. Referenzieren Sie den Webdienst DemoTemperatureService unter `http://www.xmethods.net`. Die Adresse lautet

    ```
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. Fügen Sie einen Ereignishandler für das `getTempCompleted`-Ereignis hinzu:

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > Die Anweisung `Handles` lässt sich nicht für das Zuordnen eines Ereignishandlers zu den Ereignissen des `My.WebServices`-Objekts verwenden.

3. Fügen Sie ein Feld hinzu um nachverfolgen zu können, ob der Ereignishandler dem `getTempCompleted`-Ereignis hinzugefügt wurde:

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. Fügen Sie eine Methode hinzu, um den Ereignishandler zum `getTempCompleted`-Ereignis hinzufügen – sofern nötig – und zum Aufruf der `getTempAsync`-Methode:

    ```vb
    Sub CallGetTempAsync(ByVal zipCode As Integer)
        If Not handlerAttached Then
            AddHandler My.WebServices.
                TemperatureService.getTempCompleted,
                AddressOf Me.TS_getTempCompleted
            handlerAttached = True
        End If
        My.WebServices.TemperatureService.getTempAsync(zipCode)
    End Sub
    ```

    Für einen asynchronen Aufruf der `getTemp`-Webmethode rufen Sie die `CallGetTempAsync`-Methode auf. Wenn die Webmethode fertig ist, wird ihr Rückgabewert an den `getTempCompletedHandler`-Ereignishandler übergeben.

## <a name="see-also"></a>Siehe auch

- [Zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
