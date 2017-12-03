---
title: 'Ausnahmen: Die raise-Funktion (F#)'
description: "Erfahren Sie, wie die f# \"Auslösen\" Funktion verwendet wird, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: dc524a06d075b982a6aa1fd266769bfc7d883517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="62fe9-104">Ausnahmen: Die raise-Funktion</span><span class="sxs-lookup"><span data-stu-id="62fe9-104">Exceptions: the raise Function</span></span>

<span data-ttu-id="62fe9-105">Die `raise` Funktion wird verwendet, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="62fe9-105">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="62fe9-106">Informationen zum Fehler, die in einem Ausnahmeobjekt aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="62fe9-106">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="62fe9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="62fe9-107">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="62fe9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62fe9-108">Remarks</span></span>
<span data-ttu-id="62fe9-109">Die `raise` Funktion generiert ein Exception-Objekt und eine stapelentladung Prozess initiiert.</span><span class="sxs-lookup"><span data-stu-id="62fe9-109">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="62fe9-110">Des Entladungsprozesses Stapel wird von der common Language Runtime (CLR) verwaltet, sodass das Verhalten dieses Vorgangs identisch ist, wie in jeder anderen.</span><span class="sxs-lookup"><span data-stu-id="62fe9-110">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="62fe9-111">Der Stapel Entladungsprozesses wird eine Suche nach einem Ausnahmehandler, der die generierte Ausnahme entspricht.</span><span class="sxs-lookup"><span data-stu-id="62fe9-111">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="62fe9-112">Die Suche beginnt in der aktuellen `try...with` Ausdruck, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="62fe9-112">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="62fe9-113">Jedes Muster in den `with` Block aktiviert ist, in der Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="62fe9-113">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="62fe9-114">Wenn ein passender Ausnahmehandler gefunden wird, wird die Ausnahme als behandelt. Andernfalls wird der Stapel entladen und `with` Blöcke der Aufrufkette werden überprüft, bis ein entsprechender Handler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="62fe9-114">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="62fe9-115">Alle `finally` Blöcke, die in der Aufrufkette aufgetreten sind werden ebenfalls nacheinander ausgeführt, da beim Entladen des Stapels.</span><span class="sxs-lookup"><span data-stu-id="62fe9-115">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="62fe9-116">Die `raise` Funktion entspricht der `throw` in c# oder C++.</span><span class="sxs-lookup"><span data-stu-id="62fe9-116">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="62fe9-117">Verwendung `reraise` in einem Catch-Handler die gleiche Ausnahme der Aufrufkette weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="62fe9-117">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="62fe9-118">Die folgenden Codebeispiele veranschaulichen die Verwendung der `raise` Funktion eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="62fe9-118">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="62fe9-119">Die `raise` Funktion kann auch zum Auslösen von Ausnahmen von .NET verwendet werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="62fe9-119">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="62fe9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62fe9-120">See Also</span></span>
[<span data-ttu-id="62fe9-121">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="62fe9-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="62fe9-122">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="62fe9-122">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="62fe9-123">Ausnahmen: Der `try...with`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="62fe9-123">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="62fe9-124">Ausnahmen: Der `try...finally`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="62fe9-124">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="62fe9-125">Ausnahmen: Die `failwith`-Funktion</span><span class="sxs-lookup"><span data-stu-id="62fe9-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="62fe9-126">Ausnahmen: Die `invalidArg`-Funktion</span><span class="sxs-lookup"><span data-stu-id="62fe9-126">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)