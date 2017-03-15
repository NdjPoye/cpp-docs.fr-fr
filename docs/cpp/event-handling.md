---
title: "Gestion des &#233;v&#233;nements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributs (C++), gestion des événements"
  - "gestion des événements, Visual C++"
  - "fonctions intrinsèques, gestion des événements"
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Gestion des &#233;v&#233;nements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La gestion des événements est principalement prise en charge pour les classes COM \(les classes C\+\+ qui implémentent des objets COM, généralement à l'aide de classes ATL ou de l'attribut [coclasse](../windows/coclass.md)\).  Pour plus d'informations, consultez [Gestion des événements COM](../cpp/event-handling-in-com.md).  
  
 La gestion des événements est également prise en charge pour les classes C\+\+ natives \(les classes C\+\+ qui n'implémentent pas les objets COM\). Cependant, cette prise en charge est déconseillée et sera supprimée dans une version ultérieure.  Pour plus d'informations, consultez [Gestion des événements en C\+\+ natif](../cpp/event-handling-in-native-cpp.md).  
  
 La gestion des événements prend en charge l'utilisation de thread unique et multithread et protège les données de l'accès multithread simultané.  Elle vous permet également de dériver des sous\-classes de classes de sources d'événements ou de récepteurs, et de prendre en charge la source\/réception d'événements étendue dans la classe dérivée.  
  
 Visual C\+\+ inclut des attributs et des mots clés pour déclarer des événements et des gestionnaires d'événements.  Les attributs et les mots clés d'événement peuvent être utilisés dans les programmes CLR et dans les programmes C\+\+ natifs.  
  
|Rubrique|Description|  
|--------------|-----------------|  
|[event\_source](../windows/event-source.md)|Crée une source d'événement.|  
|[event\_receiver](../windows/event-receiver.md)|Crée un récepteur d'événements \(récepteur\).|  
|[\_\_event](../cpp/event.md)|Déclare un événement.|  
|[\_\_raise](../cpp/raise.md)|Met en évidence le site d'appel d'un événement.|  
|[\_\_hook](../cpp/hook.md)|Associe une méthode de gestionnaire à un événement.|  
|[\_\_unhook](../cpp/unhook.md)|Dissocie une méthode de gestionnaire d'un événement.|  
  
## Voir aussi  
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Event Handling Samples](http://msdn.microsoft.com/fr-fr/cc0287d4-f92b-4da5-85fc-a0f186e16424)