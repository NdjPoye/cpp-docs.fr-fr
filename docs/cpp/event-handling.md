---
title: "Gestion des événements | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4167a76d3e301f76ebba09f78abcd7e64fc7f108
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling"></a>Gestion des événements
Gestion des événements sont principalement prise en charge pour les classes COM (classes C++ qui implémentent des objets COM, généralement à l’aide de classes ATL ou [coclasse](../windows/coclass.md) attribut).  Pour plus d’informations, consultez [gestion des événements COM](../cpp/event-handling-in-com.md).  
  
 La gestion des événements est également prise en charge pour les classes C++ natives (les classes C++ qui n’implémentent pas les objets COM). Cependant, cette prise en charge est déconseillée et sera supprimée dans une mise en production ultérieure.  Pour plus d’informations, consultez [gestion des événements en C++ natif](../cpp/event-handling-in-native-cpp.md).  
  
 La gestion des événements prend en charge l'utilisation de thread unique et multithread et protège les données de l'accès multithread simultané. Elle vous permet également de dériver des sous-classes de classes de sources d'événements ou de récepteurs, et de prendre en charge la source/réception d'événements étendue dans la classe dérivée.  
  
 Visual C++ inclut des attributs et des mots clés pour déclarer des événements et des gestionnaires d'événements. Les attributs et les mots clés d'événement peuvent être utilisés dans les programmes CLR et dans les programmes C++ natifs.  
  
|Rubrique|Description|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|Crée une source d'événement.|  
|[event_receiver](../windows/event-receiver.md)|Crée un récepteur d'événements (récepteur).|  
|[__event](../cpp/event.md)|Déclare un événement.|  
|[__raise](../cpp/raise.md)|Met en évidence le site d'appel d'un événement.|  
|[__hook](../cpp/hook.md)|Associe une méthode de gestionnaire à un événement.|  
|[__unhook](../cpp/unhook.md)|Dissocie une méthode de gestionnaire d'un événement.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [Exemples de gestion des événements](http://msdn.microsoft.com/en-us/cc0287d4-f92b-4da5-85fc-a0f186e16424)