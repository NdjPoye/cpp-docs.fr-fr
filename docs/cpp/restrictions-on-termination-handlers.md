---
title: "Restrictions sur les gestionnaires de terminaison | Microsoft Docs"
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
  - "restrictions, gestionnaires de terminaisons"
  - "gestionnaires de terminaisons, limitations"
  - "try-catch (mot clé) (C++), gestionnaires de terminaisons"
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Restrictions sur les gestionnaires de terminaison
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous ne pouvez pas utiliser une instruction `goto` pour accéder à un bloc d'instructions `__try` ou à un bloc d'instructions `__finally`.  À la place, vous devez entrer dans le bloc d'instruction via le flux de contrôle normal. \(Vous pouvez toutefois sauter hors d'un bloc d'instructions `__try`.\) En outre, vous ne pouvez pas imbriquer un gestionnaire d'exceptions ou un gestionnaire de terminaisons dans un bloc `__finally`.  
  
 Certains types de code autorisés dans un gestionnaire de terminaisons produisent des résultats incertains. Si vous en utilisez, faites\-le avec précaution.  Par exemple, une instruction `goto` qui saute hors d'un bloc d'instructions `__finally`.  Si le bloc s'exécute dans le cadre de l'arrêt normal, rien d'inhabituel ne se produit.  Mais si le système est en train de dérouler la pile, ce déroulement s'arrête, et la fonction actuelle prend le contrôle comme s'il n'y avait pas eu d'arrêt anormal.  
  
 Une instruction `return` dans un bloc d'instructions `__finally` présente à peu près la même situation.  Le contrôle retourne à l'appelant immédiat de la fonction contenant le gestionnaire de terminaisons.  Si le système était en train de dérouler la pile, ce processus est désactivé, et le programme continue comme si aucune exception n'était levée.  
  
## Voir aussi  
 [Écriture d'un gestionnaire des terminaisons](../cpp/writing-a-termination-handler.md)   
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)