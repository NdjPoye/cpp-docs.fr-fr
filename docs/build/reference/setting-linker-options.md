---
title: "D&#233;finition des options de l&#39;&#201;diteur de liens | Microsoft Docs"
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
  - "fichiers (C++), LINK"
  - "fichiers d'entrée (C++)"
  - "fichiers d'entrée (C++), éditeur de liens"
  - "éditeur de liens (C++), commutateurs"
  - "éditeur de liens (C++), façons de définir des options"
  - "objet/bibliothèque (modules)"
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;finition des options de l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les options de l'éditeur de liens peuvent être définies à l'intérieur ou à l'extérieur de l'environnement de développement.  La rubrique consacrée à chaque option de l'éditeur de liens explique comment définir cette option dans l'environnement de développement.  Pour la liste complète des options, consultez [Options de l'éditeur de liens](../../build/reference/linker-options.md).  
  
 Quand vous exécutez LINK en dehors de l'environnement de développement, vous pouvez spécifier l'entrée de plusieurs manières :  
  
-   Sur la [ligne de commande](../../build/reference/linker-command-line-syntax.md)  
  
-   Au moyen de [fichiers de commandes](../../build/reference/link-command-files.md)  
  
-   Dans des [variables d'environnement](../../build/reference/link-environment-variables.md)  
  
 LINK traite d'abord les options spécifiées dans la variable d'environnement LINK, suivies des autres options, dans l'ordre où elles sont spécifiées sur la ligne de commande et dans les fichiers de commandes.  Si une option est répétée avec différents arguments, le dernier argument traité est prioritaire.  
  
 Les options s'appliquent à la génération tout entière ; aucune option ne peut être appliquée à des fichiers d'entrée spécifiques.  
  
## Voir aussi  
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)