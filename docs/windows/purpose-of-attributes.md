---
title: "Purpose of Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], about attributes"
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Purpose of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les attributs étendent C\+\+ dans les instructions pas actuellement possibles sans interrompre la structure classique du langage.  Les attributs permettent aux fournisseurs distincts \(DLL\) pour étendre les fonctionnalités de langage dynamique.  L'objectif principal des attributs est de faciliter la création de composants COM, en plus de augmenter la productivité au niveau de le développeur de composants.  Les attributs peuvent être appliqués à presque tout élément C\+\+, telles que les classes, les données membres, ou des fonctions membres.  Voici une surbrillance des avantages fournies par cette nouvelle technologie :  
  
-   Expose une convention d'appel et familière simple.  
  
-   Utilise le code inséré, qui, contrairement aux macros, est identifié par le débogueur.  
  
-   Permet la dérivation facile des classes de base sans détails d'implémentation fastidieuse.  
  
-   Remplace un grand nombre de code IDL requis par un composant COM avec quelques attributs concis.  
  
 Par exemple, pour implémenter un récepteur d'événements simple pour une classe générique ATL, vous pouvez appliquer l'attribut d' [event\_receiver](../windows/event-receiver.md) à une classe spécifique par exemple `CMyReceiver`.  L'attribut d' **event\_receiver** est compilé par le compilateur Visual C\+\+, ce qui insère le code approprié dans le fichier objet.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 Vous pouvez ensuite installer les méthodes `handler1` et `handler2` de **CMyReceiver** pour gérer des événements \(à l'aide de la fonction intrinsèque [\_\_hook](../cpp/hook.md)\) d'une source d'événement, que vous pouvez créer à l'aide de [event\_source](../windows/event-source.md).  
  
## Voir aussi  
 [Concepts](../windows/attributed-programming-concepts.md)