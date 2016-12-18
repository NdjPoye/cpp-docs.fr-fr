---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1095 | Microsoft Docs"
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
  - "U1095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1095"
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ligne de commande développée 'lignecommande' trop longue  
  
 Après l'expansion macro, la ligne de commande donnée a dépassé la longueur limite des lignes de commande pour le système d'exploitation.  
  
 MS\-DOS autorise jusqu'à 128 caractères sur une ligne de commande.  
  
 Si la commande est destinée à un programme qui accepte l'entrée de ligne de commande à partir d'un fichier, modifiez la commande et fournissez l'entrée à partir d'un fichier sur le disque ou d'un fichier inline.  Par exemple, LINK et LIB acceptent une entrée provenant d'un fichier réponse.