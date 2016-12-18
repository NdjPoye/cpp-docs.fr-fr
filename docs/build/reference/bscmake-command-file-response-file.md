---
title: "BSCMAKE, fichier de commandes (fichier r&#233;ponse) | Microsoft Docs"
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
helpviewer_keywords: 
  - "BSCMAKE, fichier de commandes"
  - "BSCMAKE, fichier réponse"
  - "fichiers de commandes"
  - "fichiers de commandes, BSCMAKE"
  - "fichiers réponse"
  - "fichiers réponse, BSCMAKE"
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE, fichier de commandes (fichier r&#233;ponse)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez fournir une partie ou la totalité des données d'entrée de la ligne de commande sous la forme d'un fichier de commandes.  Spécifiez ce fichier à l'aide de la syntaxe suivante :  
  
```  
BSCMAKE @filename  
```  
  
 Un seul fichier de commandes est autorisé.  Vous pouvez spécifier un chemin d'accès avec *filename*.  Il suffit de faire précéder *filename* du signe @.  BSCMAKE n'ajoute pas d'extension de fichier par défaut.  Après le paramètre *filename*, vous pouvez spécifier d'autres *fichiers .sbr* sur la ligne de commande.  Le fichier de commandes est un fichier texte qui contient les données d'entrée pour BSCMAKE dans l'ordre où vous auriez spécifié ces données sur la ligne de commande.  Séparez les arguments de la ligne de commande par un ou plusieurs espaces, tabulations ou caractères de saut de ligne.  
  
 La commande suivante appelle BSCMAKE en utilisant un fichier de commandes :  
  
```  
BSCMAKE @prog1.txt  
```  
  
 Voici un exemple de fichier de commandes :  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## Voir aussi  
 [Référence BSCMAKE](../../build/reference/bscmake-reference.md)