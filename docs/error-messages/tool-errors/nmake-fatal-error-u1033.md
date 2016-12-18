---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1033 | Microsoft Docs"
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
  - "U1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1033"
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : 'chaîne' inattendu  
  
 La chaîne ne fait pas partie de la syntaxe valide d'un makefile.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Si les chevrons \(**\<\<**\) d'un fichier inline ne se trouvent pas au début d'une ligne, l'erreur suivante se produit :  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  Si la définition d'une macro dans le makefile contient un signe égal à \(**\=**\) sans nom qui précède ou si le nom défini est celui d'une macro qui développe une chaîne nulle, l'erreur suivante se produit :  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  Si le point\-virgule \(**;**\) dans une ligne de commentaire du fichier TOOLS.INI ne se trouve pas au début de la ligne, l'erreur suivante se produit :  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Si le makefile a été mis en forme par un programme de traitement de texte, l'erreur suivante se produit :  
  
    ```  
    syntax error : ':' unexpected  
    ```