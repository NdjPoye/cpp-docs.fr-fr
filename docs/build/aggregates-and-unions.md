---
title: "Agr&#233;gats et unions | Microsoft Docs"
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
  - "agrégats (C++), et unions"
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Agr&#233;gats et unions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

D'autres types tels que les tableaux, les structures et les unions ont des exigences plus strictes en matière d'alignement qui garantissent la cohérence du stockage d'agrégat et d'union ainsi que de la récupération des données.  Voici les définitions des termes « tableau », « structure » et « union » :  
  
 Tableau  
 Contient un groupe ordonné d'objets de données adjacents.  Chaque objet est appelé élément.  Tous les éléments contenus dans un tableau ont une taille et un type de données identiques.  
  
 Structure  
 Contient un groupe ordonné d'objets de données.  Contrairement aux éléments d'un tableau, les objets de données contenus dans une structure peuvent avoir des types de données et des tailles différents.  Chaque objet de données contenu dans une structure est appelé membre.  
  
 Union  
 Objet contenant l'un des jeux de membres nommés.  Les membres du jeu nommé peuvent être de tout type.  Le stockage alloué pour une union est égal au stockage requis pour le plus grand membre de cette union, plus tout remplissage requis pour l'alignement.  
  
 Le tableau suivant indique l'alignement vivement recommandé pour les membres scalaires d'unions et de structures.  
  
||||  
|-|-|-|  
|Type scalaire|Type de données C|Alignement requis|  
|**INT8**|`char`|Byte|  
|**UINT8**|`unsigned char`|Byte|  
|**INT16**|**short**|Word|  
|**UINT16**|**unsigned short**|Word|  
|**INT32**|**int, long**|Doubleword|  
|**UINT32**|**unsigned int, unsigned long**|Doubleword|  
|**INT64**|`__int64`|Quadword|  
|**UINT64**|**unsigned \_\_int64**|Quadword|  
|**FP32 \(simple précision\)**|**float**|Doubleword|  
|**FP64 \(double précision\)**|**double**|Quadword|  
|**POINTER**|**\***|Quadword|  
|`__m64`|**struct \_\_m64**|Quadword|  
|`__m128`|**struct \_\_m128**|Octaword|  
  
 Les règles suivantes d'alignement d'agrégats s'appliquent :  
  
-   L'alignement d'un tableau est identique à l'alignement de l'un des éléments qu'il contient.  
  
-   L'alignement du début d'une structure ou d'une union est l'alignement maximal de tout membre individuel.  Chaque membre contenu dans la structure ou l'union doit être placé à son propre alignement comme défini dans le tableau précédent qui peut exiger un remplissage interne implicite selon le membre précédent.  
  
-   La taille de la structure doit être un multiple intégral de son alignement, qui peut exiger un remplissage après le dernier membre.  Comme les structures et les unions peuvent être regroupées dans des tableaux, chaque élément de tableau d'une structure ou d'une union doit commencer et se terminer à l'alignement correct déterminé précédemment.  
  
-   Il est possible d'aligner des données afin qu'elles excèdent les exigences en matière d'alignement aussi longtemps que les règles précédentes sont conservées.  
  
-   Un compilateur individuel peut ajuster l'emballage d'une structure pour des raisons de taille.  Par exemple, [\/Zp \(Alignement des membres de la structure\)](../build/reference/zp-struct-member-alignment.md) permet d'ajuster l'emballage de structures.  
  
## Voir aussi  
 [Types et stockage](../build/types-and-storage.md)