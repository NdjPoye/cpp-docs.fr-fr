---
title: "/HEAP | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocation de tas, définir la taille des tas"
  - "HEAP (option Editbin)"
  - "-HEAP (option Editbin)"
  - "/HEAP (option Editbin)"
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HEAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit la taille du tas en octets.  Cette option s'applique uniquement aux fichiers exécutables.  
  
```  
  
/HEAP:  
reserve[,commit]  
  
```  
  
## Notes  
 L'argument `reserve` spécifie la taille totale d'allocation initiale du tas dans la mémoire virtuelle.  Par défaut, la taille du tas est de 1 Mo.  [Référence EDITBIN](../../build/reference/editbin-reference.md) arrondit la valeur spécifiée au multiple de 4 octets le plus proche.  
  
 L'argument facultatif `commit` est soumis à l'interprétation du système d'exploitation.  Sur un système d'exploitation Windows, il spécifie la valeur initiale de mémoire physique pour allouer, et la quantité de mémoire pour allouer lorsque le segment de mémoire doit être étendu.  La mémoire virtuelle dédiée fait réserver de l'espace dans le fichier d'échange.  Une valeur plus importante pour `commit` permet au système d'allouer de la mémoire moins souvent lorsque l'application a besoin de davantage d'espace mais augmente les besoins en mémoire et éventuellement le délai de démarrage de l'application.  La valeur de `commit` doit être inférieure ou égale à la valeur de `reserve`.  
  
 Spécifiez les valeurs de `reserve` et de `commit` dans le séparateur décimal ou hexadécimal du langage C ou la notation octale.  Par exemple, la valeur 1 Mo peut être spécifiée comme 1048576 en notation décimale, ou comme 0x100000 en hexadécimal, ou comme 04000000 dans octal.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)