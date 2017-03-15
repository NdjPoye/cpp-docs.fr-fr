---
title: "R&#232;gles s&#39;appliquant aux instructions de d&#233;finition de module | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers de définition de module"
  - "fichiers de définition de module, syntaxe des instructions"
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# R&#232;gles s&#39;appliquant aux instructions de d&#233;finition de module
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les règles de syntaxe suivantes s'appliquent à toutes les instructions d'un fichier .def.  D'autres règles s'appliquant à des instructions spécifiques sont décrites en même temps que celles\-ci.  
  
-   Les instructions, les mots clés des attributs et les identificateurs spécifiés par l'utilisateur respectent la casse.  
  
-   Les noms de fichiers longs contenant des espaces ou des points\-virgules \(;\) doivent être placés entre guillemets \("\).  
  
-   Utilisez un ou plusieurs espaces, tabulations ou caractères de saut de ligne pour séparer un mot clé d'instruction de ses arguments et pour séparer les instructions les unes des autres.  Un signe deux\-points \(:\) ou égal à \(\=\) qui désigne un argument est délimité par zéro ou plusieurs espaces, tabulations ou caractères de saut de ligne.  
  
-   Une instruction **NAME** ou **LIBRARY** doit, si elle est utilisée, précéder toutes les autres instructions.  
  
-   Les instructions **SECTIONS** et **EXPORTS** peuvent apparaître plusieurs fois dans le fichier .def.  Chaque instruction accepte plusieurs spécifications, qui doivent être séparées par un ou plusieurs espaces, tabulations ou caractères de saut de ligne.  Le mot clé de l'instruction doit apparaître une fois avant la première spécification et peut être répété avant chaque spécification supplémentaire.  
  
-   De nombreuses instructions ont une option de ligne de commande LINK équivalente.  Pour plus d'informations, consultez la description de l'option LINK correspondante.  
  
-   Les commentaires insérés dans le fichier .def sont signalés par un point\-virgule \(;\) au début de chaque ligne de commentaire.  Un commentaire ne peut pas partager une ligne avec une instruction, mais il peut apparaître entre les spécifications dans une instruction multiligne. \(**SECTIONS** et **EXPORTS** sont des instructions multilignes.\)  
  
-   Les arguments numériques sont spécifiés en base 10 ou hexadécimale.  
  
-   Si un argument de type chaîne correspond à un [mot réservé](../../build/reference/reserved-words.md), il doit être placé entre guillemets doubles \("\).  
  
## Voir aussi  
 [Fichiers de définition de module \(.Def\)](../../build/reference/module-definition-dot-def-files.md)   
 [Frequently Asked Questions on Building](http://msdn.microsoft.com/fr-fr/56a3bb8f-0181-4989-bab4-a07ba950ab08)