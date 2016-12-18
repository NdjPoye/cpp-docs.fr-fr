---
title: "event_source | Microsoft Docs"
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
  - "vc-attr.event_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des événements, attributs"
  - "journaux des événements, source d’événements"
  - "sources d’événements, création"
  - "event_source (attribut)"
  - "sources d'événement"
  - "gestion des événements, création de source d’événements"
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# event_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée une source d'événement.  
  
## Syntaxe  
  
```  
  
       [ event_source(  
       type,  
optimize=[speed | size],  
decorate=[true | false]) ]  
```  
  
#### Paramètres  
 `type`  
 Une énumération de l’une des valeurs suivantes :  
  
-   `native` pour le code C\/C\+\+ non managé \(par défaut pour les classes non managées\).  
  
-   `com` pour le code COM. Vous devez utiliser `coclass` quand `type`\=`com`. Cette valeur nécessite que vous incluiez les fichiers d’en\-tête suivants :  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 Quand `type` est **native**, vous pouvez spécifier **optimize\=size** pour indiquer qu’il y a quatre octets de stockage \(minimum\) pour tous les événements dans une classe ou **optimize\=speed** \(la valeur par défaut\) pour indiquer qu’il y a 4 \* \(nombre d’événements\) octets de stockage.  
  
 **decorate**  
 Quand `type` est **native**, vous pouvez spécifier **decorate\=false** pour indiquer que le nom développé dans le fichier fusionné \(.mrg\) ne doit pas inclure le nom de la classe englobante.[\/Fx](../build/reference/fx-merge-injected-code.md) vous permet de générer des fichiers .mrg.**decorate\=false**, qui est la valeur par défaut, génère des noms de types qualifiés complets dans le fichier fusionné.  
  
## Notes  
 L’attribut C\+\+ **event\_source** indique que la classe ou structure à laquelle il est appliqué est une source d’événements.  
  
 **event\_source** s’utilise conjointement avec l’attribut [event\_receiver](../windows/event-receiver.md) et le mot clé [\_\_event](../cpp/event.md). Utilisez **event\_receiver** pour créer des récepteurs d’événements. Utilisez `__event` sur les méthodes dans la source d’événements pour spécifier ces méthodes en tant qu’événements.  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## Configuration requise  
  
### Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**class**, `struct`|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclass** quand `type`\=**com**|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)