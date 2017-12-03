---
title: Verweissemantik mit Werttypen
description: Verstehen der Sprachfunktionen, die kopieren-Strukturen problemlos minimieren
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9eeaf201c1f5a58044db62e356199b609c4c035a
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="reference-semantics-with-value-types"></a><span data-ttu-id="cb325-103">Verweissemantik mit Werttypen</span><span class="sxs-lookup"><span data-stu-id="cb325-103">Reference semantics with value types</span></span>

<span data-ttu-id="cb325-104">Ein Vorteil der Verwendung von Werttypen ist, dass sie häufig Heapzuordnungen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="cb325-104">An advantage to using value types is that they often avoid heap allocations.</span></span>
<span data-ttu-id="cb325-105">Der entsprechende Nachteil ist, dass sie nach Wert kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb325-105">The corresponding disadvantage is that they are copied by value.</span></span> <span data-ttu-id="cb325-106">Dieser Nachteil erschwert die Algorithmen optimieren, die auf große Mengen an Daten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb325-106">This tradeoff makes it harder to optimize algorithms that operate on large amounts of data.</span></span> <span data-ttu-id="cb325-107">Neue Sprachfeatures in c# 7.2 Geben Mechanismen, mit denen Pass-Verweissemantik mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="cb325-107">New language features in C# 7.2 provide mechanisms that enable pass-by-reference semantics with value types.</span></span> <span data-ttu-id="cb325-108">Bei Verwendung dieser Funktionen mit Bedacht können Sie minimieren beide Zuordnungen und Kopiervorgänge.</span><span class="sxs-lookup"><span data-stu-id="cb325-108">If you use these features wisely you can minimize both allocations and copy operations.</span></span> <span data-ttu-id="cb325-109">In diesem Artikel wird erklärt, diese neuen Features.</span><span class="sxs-lookup"><span data-stu-id="cb325-109">This article explores those new features.</span></span>

<span data-ttu-id="cb325-110">Ein Großteil der Beispielcode in diesem Artikel werden die Funktionen, die in c# 7.2 hinzugefügt veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cb325-110">Much of the sample code in this article demonstrates features added in C# 7.2.</span></span> <span data-ttu-id="cb325-111">Um diese Funktionen verwenden zu können, müssen Sie das Projekt zur Verwendung von C#-7.2 oder höher in Ihrem Projekt zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cb325-111">In order to use those features, you have to configure your project to use C# 7.2 or later in your project.</span></span> <span data-ttu-id="cb325-112">Sie können Visual Studio verwenden, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="cb325-112">You can use Visual Studio to select it.</span></span> <span data-ttu-id="cb325-113">Wählen Sie für jedes Projekt **Projekt** aus dem Menü **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="cb325-113">For each project, select **Project** from the menu, then **Properties**.</span></span> <span data-ttu-id="cb325-114">Wählen Sie die **erstellen** Registerkarte, und klicken Sie auf **erweitert**.</span><span class="sxs-lookup"><span data-stu-id="cb325-114">Select the **Build** tab and click **Advanced**.</span></span> <span data-ttu-id="cb325-115">Von dort aus können Sie die Sprachversion konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cb325-115">From there, you can configure the language version.</span></span> <span data-ttu-id="cb325-116">Wählen Sie entweder "7.2" oder "Letzter".</span><span class="sxs-lookup"><span data-stu-id="cb325-116">Choose either "7.2", or "latest".</span></span>  <span data-ttu-id="cb325-117">Alternativ können Sie bearbeiten die *Csproj* Datei, und fügen Sie den folgenden Knoten:</span><span class="sxs-lookup"><span data-stu-id="cb325-117">Or you can edit the *csproj* file and add the following node:</span></span>

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

<span data-ttu-id="cb325-118">Sie können entweder "7,2" oder "Letzter" für den Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb325-118">You can use either "7.2" or "latest" for the value.</span></span>

## <a name="specifying-in-parameters"></a><span data-ttu-id="cb325-119">Angeben von `in` Parameter</span><span class="sxs-lookup"><span data-stu-id="cb325-119">Specifying `in` parameters</span></span>

<span data-ttu-id="cb325-120">7.2 c# fügt der `in` Schlüsselwort, um die vorhandene ergänzen `ref` und `out` Schlüsselwörter, wenn Sie eine Methode schreiben, die Argumente als Verweis übergibt.</span><span class="sxs-lookup"><span data-stu-id="cb325-120">C# 7.2 adds the `in` keyword to complement the existing `ref` and `out` keywords when you write a method that passes arguments by reference.</span></span> <span data-ttu-id="cb325-121">Die `in` -Schlüsselwort Gibt an, dass den Parameter als Verweis übergeben und die aufgerufene Methode nicht den Wert übergeben wird ändert.</span><span class="sxs-lookup"><span data-stu-id="cb325-121">The `in` keyword specifies that you are passing the parameter by reference and the called method does not modify the value passed to it.</span></span> 

<span data-ttu-id="cb325-122">Diese Ergänzung enthält vollständige Vokabular um Ihre Entwurfsabsicht auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="cb325-122">This addition provides a full vocabulary to express your design intent.</span></span> <span data-ttu-id="cb325-123">Werttypen werden kopiert, wenn für eine aufgerufene Methode übergeben wird, wenn Sie keinen der folgenden Modifizierer angeben.</span><span class="sxs-lookup"><span data-stu-id="cb325-123">Value types are copied when passed to a called method when you do not specify any of the following modifiers.</span></span> <span data-ttu-id="cb325-124">Jedes dieser Modifizierer anzugeben, dass ein Werttyp als Verweis übergeben wird, vermeiden die Kopie.</span><span class="sxs-lookup"><span data-stu-id="cb325-124">Each of these modifiers specify that a value type is passed by reference, avoiding the copy.</span></span> <span data-ttu-id="cb325-125">Jeder Modifizierer gibt eine andere Absicht:</span><span class="sxs-lookup"><span data-stu-id="cb325-125">Each modifier expresses a different intent:</span></span>

- <span data-ttu-id="cb325-126">`out`: Diese Methode wird der Wert des Arguments als dieser Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb325-126">`out`: This method sets the value of the argument used as this parameter.</span></span>
- <span data-ttu-id="cb325-127">`ref`: Diese Methode kann den Wert des Arguments als dieser Parameter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cb325-127">`ref`: This method may set the value of the argument used as this parameter.</span></span>
- <span data-ttu-id="cb325-128">`in`: Diese Methode ändert nicht den Wert des Arguments als dieser Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb325-128">`in`: This method does not modify the value of the argument used as this parameter.</span></span>

<span data-ttu-id="cb325-129">Beim Hinzufügen der `in` Modifizierer, um ein Argument als Verweis übergeben werden, Argumente zu übergeben, als Verweis auf das vermeiden Sie unnötige Kopieren Ihrer Entwurfsabsicht deklarieren.</span><span class="sxs-lookup"><span data-stu-id="cb325-129">When you add the `in` modifier to pass an argument by reference, you declare your design intent is to pass arguments by reference to avoid unnecessary copying.</span></span> <span data-ttu-id="cb325-130">Nicht führen Sie beabsichtigen, so ändern Sie das Objekt als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb325-130">You do not intend to modify the object used as that argument.</span></span> <span data-ttu-id="cb325-131">Der folgende Code zeigt ein Beispiel für eine Methode, die den Abstand zwischen zwei Punkten in einem 3D-Bereich berechnet.</span><span class="sxs-lookup"><span data-stu-id="cb325-131">The following code shows an example of a method that calculates the distance between two points in 3D space.</span></span> 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

<span data-ttu-id="cb325-132">Die Argumente sind zwei Strukturen, die jeweils drei Doubles enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb325-132">The arguments are two structures that each contain three doubles.</span></span> <span data-ttu-id="cb325-133">Ein Double-Wert ist 8 Byte, sodass jedes Argument 24 Bytes ist.</span><span class="sxs-lookup"><span data-stu-id="cb325-133">A double is 8 bytes, so each argument is 24 bytes.</span></span> <span data-ttu-id="cb325-134">Durch Angabe der `in` Modifizierer, übergeben Sie 4-Byte- oder 8-Byte-Verweis auf diese Argumente, je nach Architektur des Computers.</span><span class="sxs-lookup"><span data-stu-id="cb325-134">By specifying the `in` modifier, you pass 4-byte or 8-byte reference to those arguments, depending on the architecture of the machine.</span></span> <span data-ttu-id="cb325-135">Der Unterschied in Größe ist klein, aber sie können schnell summieren, wenn diese Methode in einer dichten Schleife, die mit vielen unterschiedlichen Werten von Ihrer Anwendung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cb325-135">The difference in size is small, but it can quickly add up when your application calls this method in a tight loop using many different values.</span></span>
 
<span data-ttu-id="cb325-136">Die `in` Modifizierer ergänzt `out` und `ref` auf andere Weise als auch.</span><span class="sxs-lookup"><span data-stu-id="cb325-136">The `in` modifier complements `out` and `ref` in other ways as well.</span></span> <span data-ttu-id="cb325-137">Sie können keine Überladungen einer Methode, die nur bei Vorhandensein der unterscheiden erstellen `in`, `out` oder `ref`.</span><span class="sxs-lookup"><span data-stu-id="cb325-137">You cannot create overloads of a method that differ only in the presence of `in`, `out` or `ref`.</span></span> <span data-ttu-id="cb325-138">Diese neue Regeln erweitern dasselbe Verhalten, das immer für definiert worden `out` und `ref` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb325-138">These new rules extend the same behavior that had always been defined for `out` and `ref` parameters.</span></span>

<span data-ttu-id="cb325-139">Die `in` Modifizierer kann angewendet werden, um ein Element, das Parameter annimmt: Methoden, Delegaten, Lambda-Ausdrücke, lokale Funktionen, Indexer, Operatoren.</span><span class="sxs-lookup"><span data-stu-id="cb325-139">The `in` modifier may be applied to any member that takes parameters: methods, delegates, lambdas, local functions, indexers, operators.</span></span>

<span data-ttu-id="cb325-140">Im Gegensatz zu `ref` und `out` Argumente, Sie können Literalwerte oder Konstanten für das Argument für eine `in` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb325-140">Unlike `ref` and `out` arguments, you may use literal values or constants for the argument to an `in` parameter.</span></span> <span data-ttu-id="cb325-141">Auch, im Gegensatz zu einer `ref` oder `out` Parameter verwenden, müssen Sie nicht anwenden der `in` Modifizierer an der Aufrufsite.</span><span class="sxs-lookup"><span data-stu-id="cb325-141">Also, unlike a `ref` or `out` parameter, you don't need to apply the `in` modifier at the call site.</span></span> <span data-ttu-id="cb325-142">Der folgende Code zeigt zwei Beispiele für den Aufruf der `CalculateDistance` Methode.</span><span class="sxs-lookup"><span data-stu-id="cb325-142">The following code shows you two examples of calling the `CalculateDistance` method.</span></span> <span data-ttu-id="cb325-143">Die erste Klasse verwendet zweier lokale Variablen als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="cb325-143">The first uses two local variables passed by reference.</span></span> <span data-ttu-id="cb325-144">Die zweite enthält eine temporäre Variable als Teil des Methodenaufrufs erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb325-144">The second includes a temporary variable created as part of the method call.</span></span> 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

<span data-ttu-id="cb325-145">Es gibt mehrere Möglichkeiten, die in der der Compiler stellt, dass den nur-Lese Charakter sicher ein `in` Argument wird erzwungen.</span><span class="sxs-lookup"><span data-stu-id="cb325-145">There are several ways in which the compiler ensures that the read-only nature of an `in` argument is enforced.</span></span>  <span data-ttu-id="cb325-146">Erstens, die aufgerufene Methode kann nicht direkt zuweisen einer `in` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb325-146">First of all, the called method can't directly assign to an `in` parameter.</span></span> <span data-ttu-id="cb325-147">Es kann nicht direkt auf jedes Feld der Zuweisen einer `in` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb325-147">It can't directly assign to any field of an `in` parameter.</span></span> <span data-ttu-id="cb325-148">Darüber hinaus können keine Sie übergeben ein `in` Parameter an eine beliebige Methode verlangen die `ref` oder `out` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="cb325-148">In addition, you cannot pass an `in` parameter to any method demanding the `ref` or `out` modifier.</span></span>
<span data-ttu-id="cb325-149">Der Compiler erzwingt, die die `in` Argument ist eine schreibgeschützte Variable.</span><span class="sxs-lookup"><span data-stu-id="cb325-149">The compiler enforces that the `in` argument is a readonly variable.</span></span> <span data-ttu-id="cb325-150">Sie können Instanzmethode aufrufen, die Übergabe von Wertsemantik verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb325-150">You can call any instance method that uses pass-by-value semantics.</span></span> <span data-ttu-id="cb325-151">In diesen Fällen eine Kopie der `in` wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb325-151">In those instances, a copy of the `in` parameter is created.</span></span> <span data-ttu-id="cb325-152">Da der Compiler eine temporäre Variable für eine beliebige erstellen kann `in` Parameter können auch das Angeben von Standardwerten für alle `in` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb325-152">Because the compiler can create a temporary variable for any `in` parameter, you can also specify default values for any `in` parameter.</span></span> <span data-ttu-id="cb325-153">Der folgende Code verwendet, um den Ursprung (Punkt 0,0) als Standardwert für den zweiten Punkt angeben:</span><span class="sxs-lookup"><span data-stu-id="cb325-153">The follow code uses that to specify the origin (point 0,0) as the default value for the second point:</span></span>

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

<span data-ttu-id="cb325-154">Die `in` Parameter Bezeichnung kann auch bei Verweistypen verwendet oder in numerischen Werten erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb325-154">The `in` parameter designation can also be used with reference types or built in numeric values.</span></span> <span data-ttu-id="cb325-155">Allerdings sind die Vorteile in beiden Fällen minimal, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="cb325-155">However, the benefits in both cases are minimal, if any.</span></span>

## <a name="ref-readonly-returns"></a><span data-ttu-id="cb325-156">`ref readonly`Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="cb325-156">`ref readonly` returns</span></span>

<span data-ttu-id="cb325-157">Sie sollten auch einen Werttyp als Verweis zurückgegeben, aber nicht zulassen Aufrufer aus diesen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="cb325-157">You may also want to return a value type by reference, but disallow the caller from modifying that value.</span></span> <span data-ttu-id="cb325-158">Verwenden der `ref readonly` Modifizierer, um diese Entwurfsabsicht auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="cb325-158">Use the `ref readonly` modifier to express that design intent.</span></span> <span data-ttu-id="cb325-159">Leser benachrichtigt, dass Sie einen Verweis auf die vorhandenen Daten zurückgeben, aber Änderung nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="cb325-159">It notifies readers that you are returning a reference to existing data, but not allowing modification.</span></span> 

<span data-ttu-id="cb325-160">Der Compiler erzwingt, dass der Aufrufer die Referenz ändern kann.</span><span class="sxs-lookup"><span data-stu-id="cb325-160">The compiler enforces that the caller cannot modify the reference.</span></span> <span data-ttu-id="cb325-161">Versucht, auf den Wert direkt zuweisen generieren einen Fehler während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="cb325-161">Attempts to assign to the value directly generate a compile-time error.</span></span> <span data-ttu-id="cb325-162">Der Compiler wissen nicht allerdings, wenn jeder Member-Methode den Zustand der Struktur ändert.</span><span class="sxs-lookup"><span data-stu-id="cb325-162">However, the compiler cannot know if any member method modifies the state of the struct.</span></span>
<span data-ttu-id="cb325-163">Um sicherzustellen, dass das Objekt nicht geändert wird, wird der Compiler erstellt eine Kopie und ruft Member verweisen, die mit dieser Kopie.</span><span class="sxs-lookup"><span data-stu-id="cb325-163">To ensure that the object is not modified, the compiler creates a copy and calls member references using that copy.</span></span> <span data-ttu-id="cb325-164">Alle Änderungen werden mit dieser defensiven Kopie.</span><span class="sxs-lookup"><span data-stu-id="cb325-164">Any modifications are to that defensive copy.</span></span> 

<span data-ttu-id="cb325-165">Es ist wahrscheinlich, die die Bibliothek mit `Point3D` Ursprung im gesamten Code häufig verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb325-165">It's likely that the library using `Point3D` would often use the origin throughout the code.</span></span> <span data-ttu-id="cb325-166">Jede Instanz erstellt ein neues Objekt auf dem Stapel an.</span><span class="sxs-lookup"><span data-stu-id="cb325-166">Every instance creates a new object on the stack.</span></span> <span data-ttu-id="cb325-167">Möglicherweise vorteilhaft sein, erstellen eine Konstante erstellt und als Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cb325-167">It may be advantageous to create a constant and return it by reference.</span></span> <span data-ttu-id="cb325-168">Wenn Sie einen Verweis auf die interne Speicherung zurückgeben, Sie möchten jedoch möglicherweise zu erzwingen, dass der Aufrufer den referenzierten Speicher ändern kann.</span><span class="sxs-lookup"><span data-stu-id="cb325-168">But, if you return a reference to internal storage, you may want to enforce that the caller cannot modify the referenced storage.</span></span> <span data-ttu-id="cb325-169">Der folgende Code definiert eine schreibgeschützte Eigenschaft, die zurückgibt eine `readonly ref` auf eine `Point3D` , des Ursprungs angibt.</span><span class="sxs-lookup"><span data-stu-id="cb325-169">The following code defines a read-only property that returns a `readonly ref` to a `Point3D` that specifies the origin.</span></span>

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

<span data-ttu-id="cb325-170">Erstellen eine Kopie des einen schreibgeschützten Ref return ist einfach: nur eine Variable nicht mit dem Zuweisen der `ref readonly` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="cb325-170">Creating a copy of a ref readonly return is easy: Just assign it to a variable not declared with the `ref readonly` modifier.</span></span> <span data-ttu-id="cb325-171">Der Compiler generiert Code, um das Objekt als Teil der Zuordnung zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="cb325-171">The compiler generates code to copy the object as part of the assignment.</span></span> 

<span data-ttu-id="cb325-172">Wenn Sie eine Variable zum Zuweisen einer `ref readonly return`, geben Sie entweder eine `ref readonly` Variable oder ein per-Wert-Kopie des Verweises Readonly:</span><span class="sxs-lookup"><span data-stu-id="cb325-172">When you assign a variable to a `ref readonly return`, you can specify either a `ref readonly` variable, or a by-value copy of the readonly reference:</span></span>

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

<span data-ttu-id="cb325-173">Die erste Zuweisung im vorangehenden Code wird eine Kopie der `Origin` Konstante und weist ihm, die kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb325-173">The first assignment in the preceding code makes a copy of the `Origin` constant and assigns that copy.</span></span> <span data-ttu-id="cb325-174">Die zweite weist einen Verweis.</span><span class="sxs-lookup"><span data-stu-id="cb325-174">The second assigns a reference.</span></span> <span data-ttu-id="cb325-175">Beachten Sie, dass die `readonly` Modifizierer muss Teil der Deklaration der Variablen.</span><span class="sxs-lookup"><span data-stu-id="cb325-175">Notice that the `readonly` modifier must be part of the declaration of the variable.</span></span> <span data-ttu-id="cb325-176">Der Verweis auf dem es verweist, nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cb325-176">The reference to which it refers cannot be modified.</span></span> <span data-ttu-id="cb325-177">Versuche, die dazu führen zu einem Fehler während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="cb325-177">Attempts to do so result in a compile-time error.</span></span>

## <a name="readonly-struct-type"></a><span data-ttu-id="cb325-178">`readonly struct`-Typ</span><span class="sxs-lookup"><span data-stu-id="cb325-178">`readonly struct` type</span></span>

<span data-ttu-id="cb325-179">Anwenden von `ref readonly` beim hohem Datenverkehr mithilfe einer Struktur möglicherweise nicht ausreichend.</span><span class="sxs-lookup"><span data-stu-id="cb325-179">Applying `ref readonly` to high-traffic uses of a struct may be sufficient.</span></span>
<span data-ttu-id="cb325-180">In einigen Fällen können Sie eine unveränderliche Struktur erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="cb325-180">Other times, you may want to create an immutable struct.</span></span> <span data-ttu-id="cb325-181">Anschließend können Sie immer als Readonly-Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="cb325-181">Then you can always pass by readonly reference.</span></span> <span data-ttu-id="cb325-182">Übung die Verteidigung entfernt kopiert, stattfinden beim Zugriff auf Methoden einer Struktur, die als verwendet ein `in` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb325-182">That practice removes the defensive copies that take place when you access methods of a struct used as an `in` parameter.</span></span>

<span data-ttu-id="cb325-183">Sie können dies vornehmen, indem erstellen eine `readonly struct` Typ.</span><span class="sxs-lookup"><span data-stu-id="cb325-183">You can do that by creating a `readonly struct` type.</span></span> <span data-ttu-id="cb325-184">Sie können hinzufügen, die `readonly` Modifizierer, um eine Strukturdeklaration.</span><span class="sxs-lookup"><span data-stu-id="cb325-184">You can add the `readonly` modifier to a struct declaration.</span></span> <span data-ttu-id="cb325-185">Der Compiler erzwingt, dass alle Member der Struktur `readonly`; das `struct` müssen unveränderlich sein.</span><span class="sxs-lookup"><span data-stu-id="cb325-185">The compiler enforces that all members of the struct are `readonly`; the `struct` must be immutable.</span></span>

<span data-ttu-id="cb325-186">Es gibt weitere Optimierungen für eine `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="cb325-186">There are other optimizations for a `readonly struct`.</span></span> <span data-ttu-id="cb325-187">Können Sie die `in` Modifizierer an jeder Stelle, wo ein `readonly struct` ist ein Argument.</span><span class="sxs-lookup"><span data-stu-id="cb325-187">You can use the `in` modifier at every location where a `readonly struct` is an argument.</span></span> <span data-ttu-id="cb325-188">Sie können darüber hinaus Zurückgeben einer `readonly struct` als eine `ref return` Wenn Sie ein Objekt, dessen Lebensdauer überschreitet den Bereich der Methode zurückgeben des Objekts, zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb325-188">In addition, you can return a `readonly struct` as a `ref return` when you are returning an object whose lifetime extends beyond the scope of the method returning the object.</span></span>

<span data-ttu-id="cb325-189">Schließlich generiert der Compiler effizienter Code beim Aufrufen von Membern der eine `readonly struct`: die `this` Verweis, anstatt eine Kopie der Empfänger ist immer ein `in` Parameter als Verweis auf die Membermethode übergeben.</span><span class="sxs-lookup"><span data-stu-id="cb325-189">Finally, the compiler generates more efficient code when you call members of a `readonly struct`: The `this` reference, instead of a copy of the receiver, is always an `in` parameter passed by reference to the member method.</span></span> <span data-ttu-id="cb325-190">Diese Optimierung speichert Weitere kopieren bei der Verwendung einer `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="cb325-190">This optimization saves more copying when you use a `readonly struct`.</span></span> <span data-ttu-id="cb325-191">Die `Point3D` prädestiniert für diese Änderung ist.</span><span class="sxs-lookup"><span data-stu-id="cb325-191">The `Point3D` is a great candidate for this change.</span></span> <span data-ttu-id="cb325-192">Der folgende Code zeigt ein aktualisiertes `ReadonlyPoint3D` Struktur:</span><span class="sxs-lookup"><span data-stu-id="cb325-192">The following code shows an updated `ReadonlyPoint3D` structure:</span></span>

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a><span data-ttu-id="cb325-193">`ref struct`-Typ</span><span class="sxs-lookup"><span data-stu-id="cb325-193">`ref struct` type</span></span>

<span data-ttu-id="cb325-194">Eine andere verwandte Sprachfunktion ist die Möglichkeit, einen Werttyp deklarieren, der Stapel zugeordnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="cb325-194">Another related language feature is the ability to declare a value type that must be stack allocated.</span></span> <span data-ttu-id="cb325-195">Das heißt, können dieser Typen nie auf dem Heap als Mitglied einer anderen Klasse erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cb325-195">In other words, these types can never be created on the heap as a member of another class.</span></span> <span data-ttu-id="cb325-196">Die primäre Motivation für dieses Feature wurde <xref:System.Span%601> und zugehörigen Strukturen.</span><span class="sxs-lookup"><span data-stu-id="cb325-196">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span> <span data-ttu-id="cb325-197"><xref:System.Span%601>einen verwalteten Zeiger enthalten als eines seiner Elemente, die andere wird die Länge der Spanne.</span><span class="sxs-lookup"><span data-stu-id="cb325-197"><xref:System.Span%601> may contain a managed pointer as one of its members, the other being the length of the span.</span></span> <span data-ttu-id="cb325-198">Er ist tatsächlich ein wenig anders implementiert, da C#-Zeiger in den verwalteten Speicher außerhalb von einem unsicheren Kontext nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb325-198">It's actually implemented a bit differently because C# doesn't support pointers to managed memory outside of an unsafe context.</span></span> <span data-ttu-id="cb325-199">Alle Schreibvorgänge, die ändert sich der Zeiger und die Länge ist nicht unteilbar.</span><span class="sxs-lookup"><span data-stu-id="cb325-199">Any write that changes the pointer and the length is not atomic.</span></span> <span data-ttu-id="cb325-200">Das bedeutet, dass eine <xref:System.Span%601> wäre unterliegen außerhalb des gültigen Bereichsfehler oder andere Verletzungen der typsicherheit wurden sie nicht auf einen einzelnen Stapelrahmen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="cb325-200">That means a <xref:System.Span%601> would be subject to out of range errors or other type safety violations were it not constrained to a single stack frame.</span></span> <span data-ttu-id="cb325-201">Darüber hinaus stürzt ab, in der Regel einen verwalteten Zeiger auf den GC-Heap ablegen zur JIT-Zeit.</span><span class="sxs-lookup"><span data-stu-id="cb325-201">In addition, putting a managed pointer on the GC heap typically crashes at JIT time.</span></span>

<span data-ttu-id="cb325-202">Möglicherweise ähnliche Anforderungen arbeiten mit Speicher mit erstellt [ `stackalloc` ](language-reference/keywords/stackalloc.md) oder bei der Verwendung von Arbeitsspeicher von Interop-APIs.</span><span class="sxs-lookup"><span data-stu-id="cb325-202">You may have similar requirements working with memory created using [`stackalloc`](language-reference/keywords/stackalloc.md) or when using memory from interop APIs.</span></span> <span data-ttu-id="cb325-203">Können eigene definieren `ref struct` -Typen für diese Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="cb325-203">You can define your own `ref struct` types for those needs.</span></span> <span data-ttu-id="cb325-204">In diesem Artikel finden Sie Beispiele für die Verwendung `Span<T>` aus Gründen der Einfachheit.</span><span class="sxs-lookup"><span data-stu-id="cb325-204">In this article, you see examples using `Span<T>` for simplicity.</span></span>

<span data-ttu-id="cb325-205">Die `ref struct` Deklaration deklariert, dass eine Struktur dieses Typs auf dem Stapel sein muss.</span><span class="sxs-lookup"><span data-stu-id="cb325-205">The `ref struct` declaration declares that a struct of this type must be on the stack.</span></span> <span data-ttu-id="cb325-206">Gemäß den Sprachregeln Sicherstellen der sichere Verwendung dieser Typen.</span><span class="sxs-lookup"><span data-stu-id="cb325-206">The language rules ensure the safe use of these types.</span></span> <span data-ttu-id="cb325-207">Andere Typen deklariert wird, als `ref struct` enthalten <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="cb325-207">Other types declared as `ref struct` include <xref:System.ReadOnlySpan%601>.</span></span> 

<span data-ttu-id="cb325-208">Das Ziel des durch die Beibehaltung einer `ref struct` geben, wie eine Stapel zugeordneten Variablen mehrere Regeln eingeführt, die für alle der Compiler erzwingt `ref struct` Typen.</span><span class="sxs-lookup"><span data-stu-id="cb325-208">The goal of keeping a `ref struct` type as a stack-allocated variable introduces several rules that the compiler enforces for all `ref struct` types.</span></span>

- <span data-ttu-id="cb325-209">Sie können keine Feld eine `ref struct`.</span><span class="sxs-lookup"><span data-stu-id="cb325-209">You can't box a `ref struct`.</span></span> <span data-ttu-id="cb325-210">Kann nicht zugewiesen werden eine `ref struct` Typ einer Variablen des Typs `object`, `dynamic`, oder einen beliebigen anderen Schnittstellentyp.</span><span class="sxs-lookup"><span data-stu-id="cb325-210">You cannot assign a `ref struct` type to a variable of type `object`, `dynamic`, or any interface type.</span></span>
- <span data-ttu-id="cb325-211">Sie können nicht deklariert eine `ref struct` als Member einer Klasse oder eine normale Struktur.</span><span class="sxs-lookup"><span data-stu-id="cb325-211">You can't declare a `ref struct` as a member of a class or a normal struct.</span></span>
- <span data-ttu-id="cb325-212">Lokale Variablen, die nicht deklariert werden `ref struct` Typen in Async-Methoden.</span><span class="sxs-lookup"><span data-stu-id="cb325-212">You cannot declare local variables that are `ref struct` types in async methods.</span></span> <span data-ttu-id="cb325-213">Sie deklarieren Sie diese im synchronen Methoden, mit denen `Task`, `Task<T>` oder Task-ähnlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="cb325-213">You can declare them in synchronous methods that return `Task`, `Task<T>` or Task-like types.</span></span>
- <span data-ttu-id="cb325-214">Sie können nicht deklariert werden `ref struct` lokalen Variablen in Iteratoren.</span><span class="sxs-lookup"><span data-stu-id="cb325-214">You cannot declare `ref struct` local variables in iterators.</span></span>
- <span data-ttu-id="cb325-215">Sie können keine erfassen `ref struct` Variablen in Lambda-Ausdrücken oder Funktionen.</span><span class="sxs-lookup"><span data-stu-id="cb325-215">You cannot capture `ref struct` variables in lambda expressions or local functions.</span></span>

<span data-ttu-id="cb325-216">Diese Einschränkungen stellen Sie sicher, dass Sie nicht versehentlich verwenden eine `ref struct` in einer Weise, die sie auf dem verwalteten Heap heraufzustufen konnte.</span><span class="sxs-lookup"><span data-stu-id="cb325-216">These restrictions ensure that you do not accidentally use a `ref struct` in a manner that could promote it to the managed heap.</span></span>

## <a name="conclusions"></a><span data-ttu-id="cb325-217">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cb325-217">Conclusions</span></span>

<span data-ttu-id="cb325-218">Diese Verbesserungen an der C#-Sprache sind für Leistung kritisch Algorithmen vorgesehen, in denen speicherbelegungen für die benötigte Leistung erreichen von entscheidender Bedeutung sein können.</span><span class="sxs-lookup"><span data-stu-id="cb325-218">These enhancements to the C# language are designed for performance critical algorithms where memory allocations can be critical to achieving the necessary performance.</span></span> <span data-ttu-id="cb325-219">Möglicherweise, dass Sie häufig dieser Features im Code nicht verwenden, den Sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="cb325-219">You may find that you don't often use these features in the code you write.</span></span> <span data-ttu-id="cb325-220">Allerdings haben diese Verbesserungen an zahlreichen Speicherorten in .NET Framework übernommen wurde.</span><span class="sxs-lookup"><span data-stu-id="cb325-220">However, these enhancements have been adopted in many locations in the .NET Framework.</span></span> <span data-ttu-id="cb325-221">Als weitere und weitere APIs stellen diese Funktionen nutzen möchten, sehen Sie die Leistung Ihrer eigenen Anwendungen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="cb325-221">As more and more APIs make use of these features, you'll see the performance of your own applications improve.</span></span>