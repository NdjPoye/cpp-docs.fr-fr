---
title: Objectif des attributs | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed20c29d017527d5c2ce0b0c5ab8053fc75dc6ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="purpose-of-attributes"></a>Objectif des attributs
Attributs étendent C++ dans le sens n’est pas actuellement possibles sans rompre la structure classique de la langue. Attributs permettent aux fournisseurs (DLL séparées) pour étendre les fonctionnalités de langage dynamique. L’objectif principal d’attributs est de simplifier la création de composants COM, en plus d’accroître la productivité des développeurs de composants. Les attributs peuvent être appliqués à presque n’importe quelle construction C++, telles que des classes, des membres de données ou des fonctions membres. Voici une mise en surbrillance des avantages offerts par cette nouvelle technologie :  
  
-   Expose une convention d’appel familière et simple.  
  
-   Le code inséré, qui, contrairement aux macros, est reconnue par le débogueur.  
  
-   Permet de dérivation facile à partir de classes de base sans détails d’implémentation trop complexes.  
  
-   Remplace la grande quantité de code IDL requis par un composant COM avec quelques attributs simples.  
  
 Par exemple, pour implémenter un récepteur d’événements simple pour une classe ATL générique, vous pouvez appliquer la [event_receiver](../windows/event-receiver.md) attribut à une classe spécifique, tel que `CMyReceiver`. Le **event_receiver** attribut est ensuite compilé par le compilateur Visual C++, qui insère le code approprié dans le fichier objet.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 Vous pouvez ensuite configurer le **CMyReceiver** méthodes `handler1` et `handler2` pour gérer les événements (à l’aide de la fonction intrinsèque [__hook](../cpp/hook.md)) à partir d’une source d’événement, vous pouvez créer à l’aide de [event_source](../windows/event-source.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../windows/attributed-programming-concepts.md)