---
title: "Op&#233;rateurs de pr&#233;traitement d&#39;un makefile | Microsoft Docs"
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
  - "DEFINED (opérateur)"
  - "EXIST (opérateur)"
  - "makefiles, opérateurs de prétraitement"
  - "programme NMAKE, opérateurs"
  - "opérateurs (C++), prétraitement d'un makefile"
  - "opérateurs de prétraitement des makefiles NMAKE"
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Op&#233;rateurs de pr&#233;traitement d&#39;un makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les expressions de prétraitement makefile peuvent utiliser des opérateurs qui agissent sur des valeurs constantes, les codes de sortie des commandes, chaînes, macros et chemins d'accès du système de fichiers.  Pour évaluer l'expression, le préprocesseur commence par développer les macros, puis il exécute les commandes et il effectue enfin les opérations.  Les opérations sont évaluées dans l'ordre de leur groupement explicite entre parenthèses, puis dans l'ordre de priorité des opérateurs.  Il en résulte une valeur constante.  
  
 L'opérateur `DEFINED` est un opérateur logique qui agit sur un nom de macro.  L'expression `DEFINED(`*nom\_macro*`)` est vraie si *nom\_macro* est défini, même s'il n'a pas de valeur assignée.  `DEFINED` associé à `!IF` ou `!ELSE IF` équivaut à `!IFDEF` ou `!ELSE IFDEF`.  Toutefois, à la différence de ces directives, `DEFINED` peut être utilisé dans des expressions complexes.  
  
 L'opérateur `EXIST` est un opérateur logique qui agit sur un chemin d'accès du système de fichiers.  `EXIST(`*chemin*`)` est vrai si *chemin* existe.  Le résultat d'`EXIST` peut être utilisé dans des expressions binaires.  Si *chemin* contient des espaces, placez\-le entre guillemets doubles.  
  
 Pour comparer deux chaînes, utilisez l'opérateur d'égalité \(`==`\) ou l'opérateur d'inégalité \(`!=`\).  Placez les chaînes entre guillemets doubles.  
  
 Les constantes entières peuvent utiliser les opérateurs unaires pour la négation numérique \(`–`\), le complément à un \(`~`\) et la négation logique \(`!`\).  
  
 Les expressions peuvent utiliser les opérateurs suivants.  Les opérateurs de même priorité sont regroupés ensemble et les groupes sont répertoriés dans l'ordre de priorité décroissante.  Les opérateurs unaires s'associent avec l'opérande de droite.  Les opérateurs binaires de même priorité associent les opérandes de gauche à droite.  
  
|Opérateur|Description|  
|---------------|-----------------|  
|`DEFINED(` *nom\_macro* `)`|Génère une valeur logique pour l'état de définition actuel de *nom\_macro*.|  
|`EXIST(` *chemin* `)`|Génère une valeur logique pour l'existence d'un fichier à l'emplacement *chemin*.|  
|||  
|`!`|NOT logique unaire.|  
|`~`|Complément à un unaire|  
|`-`|Négation unaire|  
|||  
|`*`|Multiplication|  
|`/`|Division|  
|`%`|Modulo \(reste\)|  
|||  
|`+`|Addition|  
|`-`|Soustraction|  
|||  
|`<<`|Déplacement à gauche au niveau du bit|  
|`>>`|Déplacement à droite au niveau du bit|  
|||  
|`<=`|Inférieur ou égal à|  
|`>=`|Supérieur ou égal à|  
|`<`|Inférieur à|  
|`>`|Supérieur à|  
|||  
|`==`|Égalité|  
|`!=`|Inégalité|  
|||  
|`&`|AND au niveau du bit|  
|`^`|XOR au niveau du bit|  
|`&#124;`|OR au niveau du bit|  
|||  
|`&&`|AND logique|  
|||  
|`&#124;&#124;`|OR logique|  
  
> [!NOTE]
>  L'opérateur XOR au niveau du bit \(`^`\) est le même que le caractère d'échappement, et il doit former une séquence d'échappement \(sous la forme `^^`\) quand il est utilisé dans une expression.  
  
## Voir aussi  
 [Expressions utilisées dans le prétraitement d'un makefile](../build/expressions-in-makefile-preprocessing.md)