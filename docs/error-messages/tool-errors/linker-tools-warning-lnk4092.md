---
title: "Avertissement des outils &#201;diteur de liens LNK4092 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4092"
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la section partagée 'section' accessible en écriture contient des réadressages ; l'image risque de ne pas s'exécuter correctement  
  
 L'éditeur de liens émet cet avertissement à chaque section partagée pour vous avertir de la possibilité de problèmes sérieux.  
  
 Une méthode de partage de données entre plusieurs processus consiste à marquer une section comme « partagée ». Mais le marquage d'une section comme partagée peut causer des problèmes.  Par exemple, si l'une de vos DLL contient des déclarations comme celle\-ci dans une section de données partagée.  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 L'éditeur de liens ne peut pas résoudre `pvar` parce que sa valeur dépend de l'emplacement de chargement de la DLL en mémoire, donc il passe un enregistrement de réadressage dans la DLL.  Quand la DLL est chargée en mémoire, l'adresse de `var` peut être résolue et `pvar` assignée.  Si un autre processus charge la même DLL mais ne peut pas le faire à la même adresse, la réaffectation de l'adresse de `var` sera mise à jour pour le second processus et l'espace d'adresses du premier processus pointera sur la mauvaise adresse.