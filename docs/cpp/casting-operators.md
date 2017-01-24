---
title: "Op&#233;rateurs de casting | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "effectuer un cast d'opérateurs"
  - "opérateurs (C++), effectuer un cast"
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs de casting
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe plusieurs opérateurs de cast spécifiques au langage C\+\+.  Ces opérateurs ont pour but de supprimer une partie de l'ambiguïté et du risque inhérents aux casts en langage C de style ancien.  Ces opérateurs sont :  
  
-   [dynamic\_cast](../cpp/dynamic-cast-operator.md) Utilisé pour la conversion des types polymorphes.  
  
-   [static\_cast](../cpp/static-cast-operator.md) Utilisé pour la conversion des types non polymorphes.  
  
-   [const\_cast](../cpp/const-cast-operator.md) Utilisé pour supprimer les attributs `const`, `volatile` et `__unaligned`.  
  
-   [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) Utilisé pour la réinterprétation simple des bits.  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) Utilisé pour produire un code MSIL vérifiable.  
  
 Utilisez `const_cast` et `reinterpret_cast` en dernier recours, car ces opérateurs présentent les mêmes risques que les casts de style ancien.  Ils sont néanmoins encore nécessaires pour remplacer complètement les casts de style ancien.  
  
## Voir aussi  
 [Effectuer un cast](../cpp/casting.md)