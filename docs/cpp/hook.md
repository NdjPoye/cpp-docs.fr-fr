---
title: "__hook | Microsoft Docs"
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
  - "__hook_cpp"
  - "__hook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__hook (mot clé) (C++)"
  - "gestionnaires d'événements, connecter les événements à"
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __hook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Associe une méthode de gestionnaire à un événement.  
  
## Syntaxe  
  
```  
  
      long __hook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]  
);  
long __hook(  
   interface,  
   source  
);  
```  
  
#### Paramètres  
 **&** *SourceClass* `::` *EventMethod*  
 Pointeur vers la méthode d'événement à laquelle vous raccordez la méthode de gestionnaire d'événements :  
  
-   Événements natifs C\+\+ : *SourceClass* est la classe d'événement source et *EventMethod* est l'événement.  
  
-   Événements COM : *SourceClass* est l'interface source d'événements et *EventMethod* est l'une de ses méthodes.  
  
-   Événements managés : *SourceClass* est la classe d'événement source et *EventMethod* est l'événement.  
  
 `interface`  
 Nom d'interface raccordé à `receiver`, uniquement pour les récepteurs d'événements COM dans lesquels le paramètre *layout\_dependent* de l'attribut [event\_receiver](../windows/event-receiver.md) est **true**.  
  
 *source*  
 Pointeur vers une instance de la source d'événement.  Selon le code `type` spécifié dans **event\_receiver**, *la source* peut être l'une des opérations suivantes :  
  
-   Un pointeur d'objet source de l'événement natif.  
  
-   Un pointeur basé sur **IUnknown**\(source COM\).  
  
-   Un pointeur d'objet managé \(pour les événements managés\).  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 Pointeur vers la méthode de gestionnaire d'événements à raccorder à un événement.  Le gestionnaire est spécifié comme une méthode d'une classe ou une référence à la même ; si vous ne spécifiez pas le nom de classe, `__hook` suppose que la classe est celle dans laquelle elle est appelée.  
  
-   Événements natifs C\+\+ : *ReceiverClass* est la classe de récepteur d'événements et `HandlerMethod` est le gestionnaire.  
  
-   Événements COM : *ReceiverClass* est l'interface du récepteur d'événements et `HandlerMethod` est l'un de ses gestionnaires.  
  
-   Événements managés : *ReceiverClass* est la classe de récepteur d'événements et `HandlerMethod` est le gestionnaire.  
  
 `receiver`\(facultatif\)  
 Pointeur vers une instance de la classe de récepteur d'événements.  Si vous ne spécifiez pas de récepteur, la valeur par défaut est la classe du récepteur ou la structure dans laquelle `__hook` est appelé.  
  
## Utilisation  
 Peut s'utiliser dans une portée de fonction quelconque, notamment Main, en dehors de la classe de récepteur d'événements.  
  
## Notes  
 Utilisez la fonction intrinsèque `__hook` dans un récepteur d'événements pour associer ou raccorder une méthode de gestionnaire à une méthode d'événement.  Le gestionnaire spécifié est ensuite appelé lorsque la source déclenche l'événement spécifié.  Vous pouvez raccorder plusieurs gestionnaires à un même événement ou raccorder plusieurs événements à un même gestionnaire.  
  
 Il existe deux formes de `__hook`.  Vous pouvez utiliser la première forme \(à quatre arguments\) dans la plupart des cas, en particulier pour les récepteurs d'événements COM dans lesquels le paramètre *layout\_dependent* de l'attribut [event\_receiver](../windows/event-receiver.md) est **false**.  
  
 Dans ces cas\-là, vous n'avez pas besoin de raccorder toutes les méthodes dans une interface avant de déclencher un événement sur l'une des méthodes ; seule la méthode qui gère l'événement doit être raccordée.  Vous pouvez utiliser la deuxième forme \(à deux arguments\) de `__hook` uniquement pour un récepteur d'événements COM dans lequel *layout\_dependent***\=true**.  
  
 `__hook` retourne une valeur de type Long.  Une valeur de retour différente de zéro indique qu'une erreur s'est produite \(les événements managés lèvent une exception\).  
  
 Le compilateur vérifie l'existence d'un événement et la conformité de la signature d'événement à la signature du délégué.  
  
 Avec l'exception des événements COM, `__hook` et `__unhook` peuvent être appelés en dehors du récepteur d'événements.  
  
 Une alternative à `__hook` consiste à utiliser l'opérateur \+\=.  
  
 Pour plus d'informations sur le codage des événements managés dans la nouvelle syntaxe, consultez [event](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## Exemple  
 Consultez [Gestion des événements en mode natif C\+\+](../cpp/event-handling-in-native-cpp.md) et [Gestion des événements dans COM](../cpp/event-handling-in-com.md) pour avoir des exemples.  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Gestion des événements](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)