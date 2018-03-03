---
title: __unhook | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unhook
- __unhook_cpp
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1513391aedf9a08cd1ece971d79fd5f6913d406d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="unhook"></a>__unhook
Dissocie une méthode de gestionnaire d'un événement.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 **&***SourceClass* `::` *EventMethod*  
 Pointeur vers la méthode d'événement à partir de laquelle vous décrochez la méthode de gestionnaire d'événements :  
  
-   Événements natifs C++ : *SourceClass* est la classe source d’événements et *EventMethod* est l’événement.  
  
-   Événements COM : *SourceClass* est l’interface de source d’événements et *EventMethod* est une de ses méthodes.  
  
-   Événements managés : *SourceClass* est la classe source d’événements et *EventMethod* est l’événement.  
  
 `interface`  
 Le nom d’interface décroché à partir `receiver`, uniquement pour les récepteurs d’événements COM dans lequel le *layout_dependent* paramètre de la [event_receiver](../windows/event-receiver.md) attribut est **true**.  
  
 *source*  
 Pointeur vers une instance de la source d'événement. En fonction du code `type` spécifié dans **event_receiver**, *source* peut prendre l’une des opérations suivantes :  
  
-   Un pointeur d'objet source de l'événement natif.  
  
-   Un **IUnknown**-en fonction de pointeur (source COM).  
  
-   Un pointeur d'objet managé (pour les événements managés).  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 Pointeur vers la méthode de gestionnaire d'événements à décrocher d'un événement. Le gestionnaire est spécifié comme une méthode d'une classe ou une référence à la même ; si vous ne spécifiez pas le nom de classe, `__unhook` suppose que la classe est celle dans laquelle elle est appelée.  
  
-   Événements natifs C++ : *ReceiverClass* est la classe de récepteur d’événements et `HandlerMethod` est le gestionnaire.  
  
-   Événements COM : *ReceiverClass* est l’interface de récepteur d’événements et `HandlerMethod` est un de ses gestionnaires.  
  
-   Événements managés : *ReceiverClass* est la classe de récepteur d’événements et `HandlerMethod` est le gestionnaire.  
  
 `receiver`(facultatif)  
 Pointeur vers une instance de la classe de récepteur d'événements. Si vous ne spécifiez pas de récepteur, la valeur par défaut est la classe du récepteur ou la structure dans laquelle `__unhook` est appelé.  
  
## <a name="usage"></a>Utilisation  
 Peut s'utiliser dans une portée de fonction quelconque, notamment Main, en dehors de la classe de récepteur d'événements.  
  
## <a name="remarks"></a>Notes  
 Utilisez la fonction intrinsèque `__unhook` dans un récepteur d'événements pour dissocier ou décrocher une méthode de gestionnaire d'une méthode d'événement.  
  
 Il existe trois formes de `__unhook`. Vous pouvez utiliser la première forme (à quatre arguments) dans la plupart des cas. Vous pouvez utiliser la deuxième forme (à deux arguments) `__unhook` uniquement pour un récepteur d'événements COM ; cela déconnecte toute l'interface d'événement. Vous pouvez utiliser la troisième forme (un argument) pour déconnecter tous les délégués de la source spécifiée.  
  
 Une valeur de retour différente de zéro indique qu'une erreur s'est produite (les événements managés lèvent une exception).  
  
 Si vous appelez `__unhook` sur un événement et que le gestionnaire d'événements n'est pas déjà raccordé, cela n'aura aucun effet.  
  
 Au moment de la compilation, le compilateur vérifie que l'événement existe et effectue la vérification du type de paramètre avec le gestionnaire spécifié.  
  
 Avec l'exception des événements COM, `__hook` et `__unhook` peuvent être appelés en dehors du récepteur d'événements.  
  
 Une alternative à `__unhook` consiste à utiliser l'opérateur -=.  
  
 Pour plus d’informations sur les événements managés dans la nouvelle syntaxe de codage, consultez [événement](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## <a name="example"></a>Exemple  
 Consultez [gestion des événements en C++ natif](../cpp/event-handling-in-native-cpp.md) et [gestion des événements COM](../cpp/event-handling-in-com.md) pour obtenir des exemples.  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__raise](../cpp/raise.md)