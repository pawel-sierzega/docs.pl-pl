---
title: "Informacje o wywołującym (F #)"
description: "Informacje dotyczące używania Caller — atrybuty Argument informacji, aby uzyskać informacje o wywołującym z metody."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a>Informacje o wywołującym

Przy użyciu atrybutów informacji o obiekcie wywołującym można uzyskać informacje o obiekcie wywołującym metodę. Można uzyskać ścieżkę pliku kodu źródłowego, numer wiersza kodu źródłowego i nazwę elementu członkowskiego obiektu wywołującego. Te informacje są przydatne do śledzenia, debugowania i tworzenia narzędzi diagnostycznych.

Aby uzyskać te informacje, należy użyć atrybutów stosowanych do opcjonalnych parametrów, z których każdy ma wartość domyślną. Poniższa tabela zawiera listę atrybutów wywołującego informacje, które są zdefiniowane w [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) przestrzeni nazw:

|Atrybut|Opis|Typ|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Pełna ścieżka pliku źródłowego zawierającego obiekt wywołujący. Jest to ścieżka pliku w czasie kompilacji.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Numer wiersza w pliku źródłowym, w którym to wierszu jest wywoływana metoda.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Nazwa metody lub właściwości obiektu wywołującego. Zobacz sekcję nazwy elementów członkowskich w dalszej części tego tematu.|`String`|

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak można użyć tych atrybutów do śledzenia obiekt wywołujący.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a>Uwagi

Caller — atrybuty informacji dotyczą wyłącznie następujące parametry opcjonalne. Należy podać wartość dla każdego parametru opcjonalnego. Atrybuty informacji wywołującego spowodować kompilator, aby zapisać poprawną wartość dla każdego parametru opcjonalnego oznaczone atrybutem wywołującego informacji.

Wartości informacji o obiekcie wywołującym są emitowane jako literały do języka pośredniego (IL, Intermediate Language) w czasie kompilacji. W odróżnieniu od wyników [ślad stosu](/dotnet/api/system.diagnostics.stacktrace) właściwości wyjątki, wyniki nie dotyczą zaciemnienie.

Można jawnie dostarczyć opcjonalne argumenty do sterowania informacjami o obiekcie wywołującym lub ukryć te informacje.

## <a name="member-names"></a>Nazwy elementów członkowskich

Można użyć [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atrybutu, aby uniknąć, określając nazwę elementu członkowskiego jako `String` argument wywołaną metodę. Przy użyciu tej metody, można uniknąć problemu, który nie zmieniają się zmienić refaktoryzacji `String` wartości. Jest to szczególnie przydatne w następujących zadaniach:

* Używanie procedur do śledzenia i diagnostycznych.
* Implementowanie [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interfejsu podczas wiązania danych. Ten interfejs umożliwia właściwości obiektu powiadamianie powiązanego formantu, że właściwość zmieniła się, dzięki czemu formant może wyświetlić zaktualizowane informacje. Bez [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atrybutu, należy określić nazwę właściwości jako literału.

W poniższej tabeli przedstawiono element członkowski nazw, które są zwracane, gdy Użyj atrybutu CallerMemberName.

|Wywołanie ma miejsce w|Wynikowa nazwa elementu członkowskiego|
|-------------------|------------------|
|Metoda, właściwość lub zdarzenie|Nazwa metody, właściwości lub zdarzenia, gdzie zainicjowane było wywołanie.|
|Konstruktor|Ciąg „.ctor”|
|Statyczny konstruktor|Ciąg „.cctor”|
|Destruktor|Ciąg „Finalize”.|
|Zdefiniowane przez użytkownika operatory lub konwersje|Nazwa wygenerowana dla elementu członkowskiego, na przykład „op_Addition”.|
|Konstruktor atrybutu|Nazwa elementu członkowskiego, do którego został zastosowany atrybut. Jeśli atrybut jest dowolnym elementem elementu członkowskiego (takim jak parametr, wartość zwracana lub parametr typu ogólnego), to wynikiem jest nazwa elementu członkowskiego, który jest skojarzony z tym elementem.|
|Brak nadrzędnego elementu członkowskiego (na przykład poziom zestawu lub atrybuty, które są stosowane do typów)|Wartość domyślna opcjonalnego parametru.|

## <a name="see-also"></a>Zobacz także
 [Atrybuty](attributes.md)  
 [Argumenty nazwane](parameters-and-arguments.md#named-arguments)  
 [Parametry opcjonalne](parameters-and-arguments.md#optional-parameters)  
