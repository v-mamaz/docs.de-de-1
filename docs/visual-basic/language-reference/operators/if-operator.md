---
title: If-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 25b0d7e85fe1c1e0d0589b4b9a9db2d85ca71526
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965901"
---
# <a name="if-operator-visual-basic"></a>If-Operator (Visual Basic)
Verwendet kurzschlussauswertung bedingt eine von zwei Werten zurück. Die `If` Operator mit drei Argumenten oder mit zwei Argumenten aufgerufen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Wenn der Operator mit drei Argumenten aufgerufen.  
 Wenn `If` wird aufgerufen, mit drei Argumenten, muss das erste Argument ein Wert, der umgewandelt werden kann ergeben eine `Boolean`. Dass `Boolean` Wert legt fest, welche der anderen beiden Argumente ausgewertet und zurückgegeben wird. Die folgende Liste gilt nur, wenn die `If` -Operator mit drei Argumenten aufgerufen wird.  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`argument1`|Erforderlich. `Boolean`. Bestimmt, welche anderen Argumente ausgewertet und zurückgegeben.|  
|`argument2`|Erforderlich. `Object`. Ausgewertet und zurückgegeben, wenn `argument1` ergibt `True`.|  
|`argument3`|Erforderlich. `Object`. Ausgewertet und zurückgegeben, wenn `argument1` ergibt `False` oder, wenn `argument1` ist eine [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` Variable, die sich ergibt [nichts](../../../visual-basic/language-reference/nothing.md).|  
  
 Ein `If` Operator, der mit drei Argumenten aufgerufen wird, funktioniert wie ein `IIf` Funktion, verwendet jedoch kurzschlussauswertung. Ein `IIf` -Funktion wertet immer alle drei Argumente, während ein `If` Operator, der drei Argumenten wertet nur zwei davon. Die erste `If` Argument wird ausgewertet, und das Ergebnis wird als Umwandeln einer `Boolean` Wert `True` oder `False`. Wenn der Wert ist `True`, `argument2` wird ausgewertet und dessen Wert zurückgegeben wird, aber `argument3` wird nicht ausgewertet. Wenn der Wert des der `Boolean` Ausdruck ist `False`, `argument3` wird ausgewertet und dessen Wert zurückgegeben wird, aber `argument2` wird nicht ausgewertet. Die folgenden Beispiele veranschaulichen die Verwendung von `If` Wenn drei Argumente verwendet werden:  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 Das folgende Beispiel zeigt den Wert der kurzschlussauswertung. Im Beispiel wird gezeigt, zwei Mal versucht, eine Variable teilen `number` Variable `divisor` Ausnahme: Wenn `divisor` ist 0 (null). In diesem Fall wird 0 zurückgegeben werden sollen, und versucht nicht, die vorgenommen werden sollen die Division ausgeführt werden, da ein Fehler zur Laufzeit führen würde. Da die `If` ausdrucksverwendungen kurzschlussauswertung ist, wird es entweder das zweite oder das dritte Argument, abhängig vom Wert des ersten Arguments. Wenn das erste Argument true ist, der Divisor ist nicht 0 (null), und es ist sicher, das zweite Argument ausgewertet, und führen Sie die Division. Wenn das erste Argument false ist, nur das dritte Argument wird ausgewertet, und 0 wird zurückgegeben. Wenn der Divisor 0 ist, wird daher kein Versuch unternommen, Durchführung der Division und tritt kein Fehler. Aber da `IIf` verwendet keine kurzschlussauswertung, das zweite Argument wird ausgewertet, auch wenn das erste Argument "false" ist. Dadurch wird ein Laufzeitfehler aufgrund einer Division durch Null.  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Wenn der Operator mit zwei Argumenten aufgerufen.  
 Das erste Argument für `If` kann ausgelassen werden. Dadurch wird den Operator mit zwei Argumenten aufgerufen werden sollen. Die folgende Liste gilt nur, wenn die `If` Operator mit zwei Argumenten aufgerufen wird.  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`argument2`|Erforderlich. `Object`. Hierbei muss es sich um eine Referenz oder nullable-Typ sein. Ausgewertet und zurückgegeben, wenn etwas anders als ergibt die Auswertung `Nothing`.|  
|`argument3`|Erforderlich. `Object`. Ausgewertet und zurückgegeben, wenn `argument2` ergibt `Nothing`.|  
  
 Wenn die `Boolean` Argument ausgelassen wird, wird das erste Argument eine Referenz oder nullable-Typ sein muss. Wenn das erste Argument ergibt `Nothing`, der Wert des zweiten Arguments wird zurückgegeben. In allen anderen Fällen wird der Wert des ersten Arguments zurückgegeben. Im folgende Beispiel wird veranschaulicht, wie diese Auswertung funktioniert.  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
