---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2440f322ea7dbd3a6d6f9d56878273c49b26bfa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
Zachowanie usługi sterująca po zwolnione wystąpienia bezczynności przepływu pracy i utrwalone.  
  
\<System. ServiceModel >  
\<zachowania >  
\<serviceBehaviors >  
\<zachowanie >  
\<workflowIdle >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|timeToPersist|Wartość Timespan określający okres czasu, między czasem przepływu pracy, staje się bezczynności i jest trwały. Wartość domyślna to wartość TimeSpan.MaxValue.<br /><br /> Czas trwania rozpoczyna upłynąć, gdy wystąpienie przepływu pracy staje się nieaktywna. Ten atrybut jest przydatne, jeśli chcesz bardziej agresywnie utrwalenie wystąpienia przepływu pracy, jednocześnie zachowując wystąpienia w pamięci tak długo, jak to możliwe. Ten atrybut jest tylko wtedy, gdy jego wartość jest mniejsza niż **timeToUnload** atrybutu. Jeśli jest większa, jest ignorowana. Jeśli ten atrybut, który musi upłynąć przed wartość określoną przez **timeToUnload** atrybutu trwałości należy wykonać przed przepływ pracy zostanie zwolniony. Oznacza to, że operacja zwolnienia mogą być opóźnione aż do przepływu pracy jest trwały. Warstwa trwałości jest odpowiedzialny za obsługę dowolnego powtórzeń przejściowy błędów i tylko na błędy bez nieodwracalny zgłasza wyjątek wyjątków. Dlatego wyjątki zgłaszane w trwałości są traktowane jako krytyczny, a wystąpienie przepływu pracy zostało przerwane.|  
|timeToUnload|Zakres czasu wartość, która określa czas trwania między czas przepływu pracy staje się bezczynności i jest zwalniana. Wartość domyślna to 1 minutę.<br /><br /> Zwalnianie przepływu pracy oznacza to również utrwalone. Ten atrybut jest ustawiony na zero, wystąpienie przepływu pracy jest utrwalona i zwalnianie natychmiast po przepływu pracy, staje się bezczynności. Ustawienie tego atrybutu na wartość TimeSpan.MaxValue skutecznie wyłącza operacja zwolnienia. Wystąpienia przepływu pracy bezczynności nigdy nie są usuwane.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<zachowanie > z \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Określa zachowanie elementu.|  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
