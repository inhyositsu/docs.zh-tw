---
title: let 繫結 (F#)
description: "了解如何使用 F # 'let' 繫結，其值或函式使用關聯識別項。"
ms.date: 05/16/2016
ms.openlocfilehash: bcdf01747c2a1d0ba9a894188dae1d42acdf9104
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566268"
---
# <a name="let-bindings"></a>let 繫結

A*繫結*關聯的值或函式的識別項。 您使用`let`關鍵字來繫結至值或函式的名稱。

## <a name="syntax"></a>語法

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>備註

`let`關鍵字用於繫結來定義值或一或多個名稱的函式值的運算式。 最簡單的形式`let`運算式繫結名稱為簡單的值，如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

如果您使用新的一行分隔識別碼中的運算式，您必須縮排每一行的運算式，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

而不是只有名稱，您可以指定包含名稱的模式，例如，一個 tuple，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

*主體運算式*是該名稱使用的運算式。 本文顯示此運算式的那一行，並將其與中的第一個字元完全縮排成線條向上`let`關鍵字：

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

A`let`繫結可以出現在模組層級定義中的類別類型，或在本機的範圍，例如內嵌函式定義。 A`let`在最上層的類別類型或模組中的繫結不需要具有主體運算式，但其他範圍層級中，主體必須是運算式。 繫結的名稱會使用點定義，但不是在之前的任何時間點之後`let`出現繫結，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a>函式繫結

函式繫結會遵循值的繫結規則，不同之處在於函式繫結包含函式名稱和參數，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

一般情況下，參數為模式，例如 tuple 模式：

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

A`let`繫結運算式評估為最後一個運算式的值。 因此，在下列程式碼範例中，值`result`計算從`100 * function3 (1, 2)`，這會評估為`300`。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

如需詳細資訊，請參閱[函式](index.md)。

## <a name="type-annotations"></a>型別附註

您可以指定類型的參數包含冒號 （:） 後面接著類型名稱，所有括在括號中。 您也可以在最後一個參數後附加冒號和型別，以指定傳回值的類型。 完整的類型註釋`function1`，以做為參數類型的整數，將會如下。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

沒有明確的型別參數時，型別推斷會判斷函式的參數型別。 這可能包括自動一般化 設為泛型參數的類型。

如需詳細資訊，請參閱[自動一般化](../generics/automatic-generalization.md)和[型別推斷](../type-inference.md)。

## <a name="let-bindings-in-classes"></a>類別中的 let 繫結

A`let`繫結可以出現在類別類型，但不是在結構或記錄類型。 若要使用的類別類型中的繫結可讓，類別必須具有主要建構函式。 建構函式參數必須出現在類別定義中的類型名稱之後。 A`let`類別型別中的繫結定義私用欄位和成員，該類別類型，並搭配`do`類型中的繫結表單類型的主要建構函式的程式碼。 下列程式碼範例顯示類別`MyClass`與私用欄位`field1`和`field2`。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

範圍`field1`和`field2`僅限於在宣告的型別。 如需詳細資訊，請參閱[`let`類別中的繫結](../members/let-bindings-in-classes.md)和[類別](../classes.md)。

## <a name="type-parameters-in-let-bindings"></a>型別參數中的 let 繫結

A`let`繫結，在模組層級，在類型中，或計算運算式中可以有明確的型別參數。 中的繫結運算式，例如函式定義內可讓不能有型別參數。 如需詳細資訊，請參閱[泛型](../generics/index.md)。

## <a name="attributes-on-let-bindings"></a>上的屬性 let 繫結

屬性可以套用至最上層`let`繫結，在模組中，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a>領域和存取範圍 Let 繫結

Let 繫結所宣告的實體的範圍僅限於包含的部分繫結出現後 （例如函式、 模組、 檔案或類別） 的範圍。 因此，它可說是 let 繫結引進一個名稱，進入範圍內。 在模組中，讓繫結值或函式是模組的用戶端可以存取，只要模組可供存取，因為模組中的 let 繫結會編譯成模組的公用函式。 相反地，類別中的 let 繫結是私用類別。

一般來說，模組中的函式必須使用用戶端程式碼時的模組名稱所限定。 例如，如果模組`Module1`有函式`function1`，使用者就必須指定`Module1.function1`到參考的函式。

模組的使用者可以使用匯入宣告而不以模組名稱所限定，使該模組內的函式可供使用。 在上述範例中，模組的使用者可以在此情況下開啟模組使用匯入宣告開啟`Module1`，而且此後參考`function1`直接。

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

某些模組具有屬性[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)，這表示它們公開的函式必須以模組名稱加以限定。 例如，F # 清單模組有這個屬性。

如需有關模組和存取控制的詳細資訊，請參閱[模組](../modules.md)和[存取控制](../access-control.md)。

## <a name="see-also"></a>另請參閱

[函式](index.md)

[類別中的 `let` 繫結](../members/let-bindings-in-classes.md)
