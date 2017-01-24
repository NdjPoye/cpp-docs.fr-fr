---
title: "__unhook | Microsoft Docs"
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
  - "__unhook"
  - "__unhook_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unhook (mot clé) (C++)"
  - "gestionnaires d'événements, dissocier des événements"
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __unhook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dissocie une méthode de gestionnaire d'un événement.  
  
## Syntaxe  
  
```  
  
      long  __unhook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]   
);  
long  __unhook(   
   interface,  
   source  
);  
long  __unhook(  
   source   
);  
```  
  
#### Paramètres  
 **&** *SourceClass* `::` *EventMethod*  
 Pointeur vers la méthode d'événement à partir de laquelle vous décrochez la méthode de gestionnaire d'événements :  
  
-   Événements natifs C\+\+ : *SourceClass* est la classe d'événement source et *EventMethod* est l'événement.  
  
-   Événements COM : *SourceClass* est l'interface source d'événements et *EventMethod* est l'une de ses méthodes.  
  
-   Événements managés : *SourceClass* est la classe d'événement source et *EventMethod* est l'événement.  
  
 `interface`  
 Nom d'interface décroché à partir de `receiver`, uniquement pour les récepteurs d'événements COM dans lesquels le paramètre *layout\_dependent* de l'attribut [event\_receiver](../windows/event-receiver.md) est **true**.  
  
 *source*  
 Pointeur vers une instance de la source d'événement.  Selon le code `type` spécifié dans **event\_receiver**, *source* peut être l'un des éléments suivants :  
  
-   Un pointeur d'objet source de l'événement natif.  
  
-   Un pointeur basé sur **IUnknown**\(source COM\).  
  
-   Un pointeur d'objet managé \(pour les événements managés\).  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 Pointeur vers la méthode de gestionnaire d'événements à décrocher d'un événement.  Le gestionnaire est spécifié comme une méthode d'une classe ou une référence à la même ; si vous ne spécifiez pas le nom de classe, `__unhook` suppose que la classe est celle dans laquelle elle est appelée.  
  
-   Événements natifs C\+\+ : *ReceiverClass* est la classe de récepteur d'événements et `HandlerMethod` est le gestionnaire.  
  
-   Événements COM : *ReceiverClass* est l'interface du récepteur d'événements et `HandlerMethod` est l'un de ses gestionnaires.  
  
-   Événements managés : *ReceiverClass* est la classe de récepteur d'événements et `HandlerMethod` est le gestionnaire.  
  
 `receiver`\(facultatif\)  
 Pointeur vers une instance de la classe de récepteur d'événements.  Si vous ne spécifiez pas de récepteur, la valeur par défaut est la classe du récepteur ou la structure dans laquelle `__unhook` est appelé.  
  
## Utilisation  
 Peut s'utiliser dans une portée de fonction quelconque, notamment Main, en dehors de la classe de récepteur d'événements.  
  
## Notes  
 Utilisez la fonction intrinsèque `__unhook` dans un récepteur d'événements pour dissocier ou décrocher une méthode de gestionnaire d'une méthode d'événement.  
  
 Il existe trois formes de `__unhook`.  Vous pouvez utiliser la première forme \(à quatre arguments\) dans la plupart des cas.  Vous pouvez utiliser la deuxième forme \(à deux arguments\) `__unhook` uniquement pour un récepteur d'événements COM ; cela déconnecte toute l'interface d'événement.  Vous pouvez utiliser la troisième forme \(un argument\) pour déconnecter tous les délégués de la source spécifiée.  
  
 Une valeur de retour différente de zéro indique qu'une erreur s'est produite \(les événements managés lèvent une exception\).  
  
 Si vous appelez `__unhook` sur un événement et que le gestionnaire d'événements n'est pas déjà raccordé, cela n'aura aucun effet.  
  
 Au moment de la compilation, le compilateur vérifie que l'événement existe et effectue la vérification du type de paramètre avec le gestionnaire spécifié.  
  
 Avec l'exception des événements COM, `__hook` et `__unhook` peuvent être appelés en dehors du récepteur d'événements.  
  
 Une alternative à `__unhook` consiste à utiliser l'opérateur \-\=.  
  
 Pour plus d'informations sur le codage des événements managés dans la nouvelle syntaxe, consultez [event](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## Exemple  
 Consultez [Gestion des événements en mode natif C\+\+](../cpp/event-handling-in-native-cpp.md) et [Gestion des événements dans COM](../cpp/event-handling-in-com.md) pour avoir des exemples.  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_raise](../cpp/raise.md)