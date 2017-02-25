---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1035"
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable NMAKE U1035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : séparateur ':' ou '\=' attendu  
  
 Un signe des deux\-points \(**:**\) ou un signe égal à \(**\=**\) était attendu.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Une cible n'est pas suivie par un signe des deux\-points.  
  
2.  Une cible composée d'une seule lettre est suivie par un signe des deux\-points sans espace \(par exemple, a:\).  NMAKE interprète cela comme une spécification de lecteur.  
  
3.  Une règle d'inférence n'est pas suivie par un signe des deux\-points.  
  
4.  Une définition de macro n'est pas suivie par un signe égal à.  
  
5.  Un caractère suit une barre oblique inverse \(**\\**\) utilisée pour qu'une commande continue sur une nouvelle ligne.  
  
6.  La chaîne qui apparaît n'obéit à aucune règle de syntaxe NMAKE.  
  
7.  Le makefile a été mis en forme par un programme de traitement de texte.