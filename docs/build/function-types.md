---
title: "Types de fonctions | Microsoft Docs"
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
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Types de fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe principalement deux types de fonctions.  Une fonction exigeant un frame de pile est appelée fonction de frame.  Une fonction qui n'exige pas de frame de pile est appelée fonction feuille.  
  
 Une fonction de frame est une fonction qui alloue de l'espace de pile, appelle d'autres fonctions, enregistre des registres non volatils ou utilise la gestion des exceptions.  Elle requiert également une entrée de table de fonctions.  Une fonction de frame exige un prologue et un épilogue.  Elle peut allouer de l'espace de pile dynamiquement et employer un pointeur de frame.  Une fonction de frame dispose de l'intégralité des possibilités offertes pare cette norme d'appel.  
  
 Si une fonction de frame n'appelle pas ensuite une autre fonction, il n'est alors pas nécessaire d'aligner la pile \(comme décrit à la section [Allocation de piles](../build/stack-allocation.md)\).  
  
 Une fonction feuille ne requiert pas d'entrée de table de fonctions.  Elle ne peut pas appeler de fonction, allouez d'espace ou enregistrer de registres non volatils.  Elle est autorisée à laisser la pile non alignée lors de son exécution.  
  
## Voir aussi  
 [Utilisation de la pile](../build/stack-usage.md)