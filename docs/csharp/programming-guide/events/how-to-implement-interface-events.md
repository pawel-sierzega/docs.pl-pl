---
title: "Porady: zdarzenia implementowania interfejsu (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a53c6ba29837ad8827d97ea745be0462451eb145
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Porady: zdarzenia implementowania interfejsu (Przewodnik programowania w języku C#)
[Interfejsu](../../../csharp/language-reference/keywords/interface.md) mogą zadeklarować [zdarzeń](../../../csharp/language-reference/keywords/event.md). Poniższy przykład pokazuje, jak można zaimplementować interfejsu zdarzenia w klasie. Zasadniczo zasad są takie same jak podczas implementowania interfejsu metody ani właściwości.  
  
### <a name="to-implement-interface-events-in-a-class"></a>Aby zaimplementować interfejsu zdarzenia w klasie  
  
-   Deklarowanie zdarzenia w klasie i wywołać go w odpowiednich obszarach.  
  
    ```csharp
    namespace ImplementInterfaceEvents  
    {  
        public interface IDrawingObject  
        {  
            event EventHandler ShapeChanged;  
        }  
        public class MyEventArgs : EventArgs   
        {  
            // class members  
        }  
        public class Shape : IDrawingObject  
        {  
            public event EventHandler ShapeChanged;  
            void ChangeShape()  
            {  
                // Do something here before the event…  
  
                OnShapeChanged(new MyEventArgs(/*arguments*/));  
  
                // or do something here after the event.   
            }  
            protected virtual void OnShapeChanged(MyEventArgs e)  
            {  
                if(ShapeChanged != null)  
                {  
                   ShapeChanged(this, e);  
                }  
            }  
        }  
  
    }  
    ```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia sposób obsługi mniej typowe sytuacji, w którym klasa dziedziczy z dwóch lub więcej interfejsów i każdy interfejs ma zdarzenia o takiej samej nazwie. W takiej sytuacji należy dostarczyć jawnej implementacji interfejsu dla co najmniej jednego zdarzenia. Podczas pisania jawnej implementacji interfejsu zdarzenia musi także zapisywać `add` i `remove` metod dostępu zdarzeń. Zwykle te są dostarczane przez kompilator, ale w takim przypadku kompilator nie można udostępnić je.  
  
 Podając własne metody dostępu, można określić, czy dwa zdarzenia są reprezentowane przez tego samego zdarzenia w klasie lub różnych zdarzeń. Na przykład jeśli zdarzenia powinien być wywoływany w różnych momentach zgodnie ze specyfikacją określoną interfejsu, można skojarzyć każdego zdarzenia z implementacją oddzielne w klasie. W poniższym przykładzie subskrybentów określenie `OnDraw` zdarzeń otrzymywanych przez rzutowanie odwołanie kształtu do albo `IShape` lub `IDrawingObject`.  
  
 [!code-csharp[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]  
  
## <a name="see-also"></a>Zobacz też  
 [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
 [Zdarzenia](../../../csharp/programming-guide/events/index.md)  
 [Delegaci](../../../csharp/programming-guide/delegates/index.md)  
 [Implementacja interfejsu jawnego](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 [Instrukcje: wywoływanie zdarzeń klasy podstawowej w klasach pochodnych](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
