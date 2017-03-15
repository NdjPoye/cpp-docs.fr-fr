---
title: "Macros de variables d&#39;environnement | Microsoft Docs"
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
  - "variables d'environnement, macros dans NMAKE"
  - "macros, variable d'environnement"
  - "programme NMAKE, macros de variables d'environnement"
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Macros de variables d&#39;environnement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE hérite des définitions de macros pour les variables d'environnement qui existaient avant l'ouverture de la session.  Si une variable a été définie dans l'environnement du système d'exploitation, elle est disponible en tant que macro NMAKE.  Les noms hérités sont convertis en majuscules.  L'héritage intervient avant le prétraitement.  Utilisez l'option \/E pour que les macros héritées de variables d'environnement substituent éventuellement les macros du makefile portant le même nom.  
  
 Les macros de variables d'environnement sont redéfinies au cours de la session, ce qui modifie la variable d'environnement correspondante.  Vous pouvez également modifier les variables d'environnement à l'aide de la commande SET.  L'utilisation de la commande SET pour modifier une variable d'environnement pendant la session ne modifie, cependant, pas la macro correspondante.  
  
 Par exemple :  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 Dans cet exemple, la modification de `PATH` s'accompagne de la modification de la variable d'environnement correspondante `PATH` ; elle ajoute `\nonesuch` au chemin.  
  
 Si une variable d'environnement est définie en tant que chaîne pouvant être incorrecte sur le plan de la syntaxe dans un makefile, aucune macro n'est créée et aucun avertissement n'est émis.  Si une valeur de variable contient un signe dollar \($\), NMAKE l'interprète en tant que début d'appel d'une macro.  L'utilisation de la macro peut induire un comportement inattendu.  
  
## Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)