---
title: __hook | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __hook
dev_langs:
- C++
helpviewer_keywords:
- __hook keyword [C++]
- event handlers, connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 21bb75853d8664ad46bc48fc907946ae5a147f9a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="hook"></a>__hook
Associe une méthode de gestionnaire à un événement.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 **&***SourceClass* `::` *EventMethod*  
 Pointeur vers la méthode d'événement à laquelle vous raccordez la méthode de gestionnaire d'événements :  
  
-   Événements natifs C++ : *SourceClass* est la classe source d’événements et *EventMethod* est l’événement.  
  
-   Événements COM : *SourceClass* est l’interface de source d’événements et *EventMethod* est une de ses méthodes.  
  
-   Événements managés : *SourceClass* est la classe source d’événements et *EventMethod* est l’événement.  
  
 `interface`  
 Le nom d’interface raccordé à `receiver`, uniquement pour les récepteurs d’événements COM dans lequel le *layout_dependent* paramètre de la [event_receiver](../windows/event-receiver.md) attribut est **true**.  
  
 *source*  
 Pointeur vers une instance de la source d'événement. En fonction du code `type` spécifié dans **event_receiver**, *source* peut prendre l’une des opérations suivantes :  
  
-   Un pointeur d'objet source de l'événement natif.  
  
-   Un **IUnknown**-en fonction de pointeur (source COM).  
  
-   Un pointeur d'objet managé (pour les événements managés).  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 Pointeur vers la méthode de gestionnaire d'événements à raccorder à un événement. Le gestionnaire est spécifié comme une méthode d'une classe ou une référence à la même ; si vous ne spécifiez pas le nom de classe, `__hook` suppose que la classe est celle dans laquelle elle est appelée.  
  
-   Événements natifs C++ : *ReceiverClass* est la classe de récepteur d’événements et `HandlerMethod` est le gestionnaire.  
  
-   Événements COM : *ReceiverClass* est l’interface de récepteur d’événements et `HandlerMethod` est un de ses gestionnaires.  
  
-   Événements managés : *ReceiverClass* est la classe de récepteur d’événements et `HandlerMethod` est le gestionnaire.  
  
 `receiver`(facultatif)  
 Pointeur vers une instance de la classe de récepteur d'événements. Si vous ne spécifiez pas de récepteur, la valeur par défaut est la classe du récepteur ou la structure dans laquelle `__hook` est appelé.  
  
## <a name="usage"></a>Utilisation  
 Peut s'utiliser dans une portée de fonction quelconque, notamment Main, en dehors de la classe de récepteur d'événements.  
  
## <a name="remarks"></a>Remarques  
 Utilisez la fonction intrinsèque `__hook` dans un récepteur d'événements pour associer ou raccorder une méthode de gestionnaire à une méthode d'événement. Le gestionnaire spécifié est ensuite appelé lorsque la source déclenche l'événement spécifié. Vous pouvez raccorder plusieurs gestionnaires à un même événement ou raccorder plusieurs événements à un même gestionnaire.  
  
 Il existe deux formes de `__hook`. Vous pouvez utiliser la première forme (à quatre arguments) dans la plupart des cas, en particulier, pour les récepteurs d’événements COM dans lequel le *layout_dependent* paramètre de la [event_receiver](../windows/event-receiver.md) attribut est **false **.  
  
 Dans ces cas-là, vous n'avez pas besoin de raccorder toutes les méthodes dans une interface avant de déclencher un événement sur l'une des méthodes ; seule la méthode qui gère l'événement doit être raccordée. Vous pouvez utiliser la deuxième forme (à deux arguments) de `__hook` uniquement pour un récepteur d’événements COM dans lequel *layout_dependent***= true**.  
  
 `__hook` retourne une valeur de type Long. Une valeur de retour différente de zéro indique qu'une erreur s'est produite (les événements managés lèvent une exception).  
  
 Le compilateur vérifie l'existence d'un événement et la conformité de la signature d'événement à la signature du délégué.  
  
 Avec l'exception des événements COM, `__hook` et `__unhook` peuvent être appelés en dehors du récepteur d'événements.  
  
 Une alternative à `__hook` consiste à utiliser l'opérateur +=.  
  
 Pour plus d’informations sur les événements managés dans la nouvelle syntaxe de codage, consultez [événement](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## <a name="example"></a>Exemple  
 Consultez [gestion des événements en C++ natif](../cpp/event-handling-in-native-cpp.md) et [gestion des événements COM](../cpp/event-handling-in-com.md) pour obtenir des exemples.  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [Gestion des événements](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)
