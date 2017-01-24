---
title: "/STACK | Microsoft Docs"
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
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STACK (option Editbin)"
  - "STACK (option Editbin)"
  - "-STACK (option Editbin)"
  - "pile, définir la taille"
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /STACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## Notes  
 Cette option définit la taille de la pile en octets et accepte des arguments en notation décimale ou de langage C.  L'option \/STACK s'applique uniquement à un fichier exécutable.  
  
 L'argument *reserve* spécifie la taille totale d'allocation de piles dans la mémoire virtuelle.  EDITBIN arrondit la valeur spécifiée aux 4 octets les plus proches.  
  
 L'argument facultatif `commit` est soumis à l'interprétation du système d'exploitation.  Sous Windows NT, Windows 95 et Windows 98, `commit` spécifie la quantité de mémoire physique à allouer dans chaque cas.  La mémoire virtuelle dédiée fait réserver de l'espace dans le fichier d'échange.  Une valeur `commit` supérieure permet de gagner du temps quand l'application requiert davantage d'espace pour la pile mais augmente les besoins en ressources mémoire et peut allonger la durée de la phase de démarrage.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)