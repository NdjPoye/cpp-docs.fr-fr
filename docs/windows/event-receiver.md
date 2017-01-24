---
title: "event_receiver | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.event_receiver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event_receiver attribute"
  - "event receivers"
  - "events [C++], event receivers (sinks)"
  - "event handling [C++], attributes"
  - "event handling [C++], creating receiver"
  - "event sinks, creating"
  - "event sinks"
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# event_receiver
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

crée un récepteur d'événements \(récepteur\).  
  
## Syntaxe  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### Paramètres  
 `type`  
 une énumération d'une des valeurs suivantes :  
  
-   `native` pour du code non managé C\/C\+\+ \(valeur par défaut pour les classes natives\).  
  
-   `com` pour le code de COM.  cette valeur requiert que vous incluez les fichiers d'en\-tête suivants :  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout\_dependent**  
 Spécifiez *layout\_dependent* uniquement si `type`\=**COM**.  *layout\_dependent* est une valeur booléenne :  
  
-   **true** signifie que la signature du récepteur de délégués dans l'événement doit correspondre exactement à ceux auxquels il est dans le source lié.  Les noms des gestionnaires de récepteur d'événements doivent correspondre à ceux spécifiés dans l'interface appropriée de l'événement.  vous devez utiliser **coclasse** si *layout\_dependent* est **true**.  il est légèrement plus efficace de spécifier **true**.  
  
-   **false** \(valeur par défaut\) signifie que la convention d'appel et la classe de stockage \(virtuel, statique, etc.\) ne doivent pas correspondre à la méthode d'événement et les gestionnaires ; ni effectuent le gestionnaire que les noms doivent correspondre aux noms des méthodes d'interface de l'événement.  
  
## Notes  
 L'attribut d' **event\_receiver** C\+\+ spécifie que la classe ou la structure dans laquelle il est appliqué est un récepteur d'événements, à l'aide de le modèle d'événement unifié par Visual C\+\+.  
  
 **event\_receiver** est utilisé avec l'attribut d' [event\_source](../windows/event-source.md) et les mots clés de [\_\_hook](../cpp/hook.md) et de [\_\_unhook](../cpp/unhook.md) .  utilisation **event\_source** de créer des sources d'événement.  Utilisez `__hook` dans les méthodes d'un récepteur d'événements pour associer \(« raccordement »\) des méthodes de récepteur d'événements aux événements d'une source d'événement.  utilisation `__unhook` de les dissocier.  
  
 *layout\_dependent* n'est spécifié pour les récepteurs d'événements COM \(`type`\=**COM**\).  la valeur par défaut pour *layout\_dependent* est **false**.  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|**coclasse** lorsque layout\_dependent\=**true**|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_source](../windows/event-source.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)