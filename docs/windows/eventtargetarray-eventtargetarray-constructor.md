---
title: "EventTargetArray::EventTargetArray, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray, constructeur"
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray::EventTargetArray, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### Paramètres  
 `hr`  
 Après les opérations de ce constructeur, le paramètre `hr` indique si l'allocation du tableau a réussi ou échoué.  Le tableau suivant énumère les valeurs possibles pour `hr`.  
  
 S\_OK  
 L'opération a réussi.  
  
 E\_OUTOFMEMORY  
 Aucune mémoire n'a pu être allouée pour le tableau.  
  
 S\_FALSE  
 Le paramètre `items` est inférieur ou égal à zéro.  
  
 `items`  
 Le nombre d'éléments du tableau à allouer.  
  
## Remarques  
 Initialise une nouvelle instance de la classe EventTargetArray.  
  
 EventTargetArray permet de conserver un tableau de gestionnaires d'événements dans un objet EventSource.  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [EventTargetArray, classe](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)