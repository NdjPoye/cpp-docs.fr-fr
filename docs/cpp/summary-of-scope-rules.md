---
title: "R&#233;sum&#233; des r&#232;gles de port&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "noms de classes (C++), règles de portée"
  - "portée de classe (C++), règles"
  - "classes (C++), portée"
  - "noms (C++), de classes"
  - "portée (C++), noms de classes"
ms.assetid: 47e26482-0111-466f-b857-598c15d05105
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;sum&#233; des r&#232;gles de port&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation d'un nom doit être non équivoque dans sa portée \(jusqu'au point où la surcharge est déterminée\).  Si le nom indique une fonction, celle\-ci doit être non équivoque en ce qui concerne le nombre et le type de paramètres.  Si le nom n'est pas ambigu, les règles d'[accès aux membres](../cpp/member-access-control-cpp.md) sont appliquées.  
  
## Initialiseurs de constructeur  
 Les initialiseurs de constructeur \(décrits dans [Initialisation des bases et des membres](http://msdn.microsoft.com/fr-fr/2f71377e-2b6b-49da-9a26-18e9b40226a1)\) sont évalués dans la portée du bloc le plus à l'extérieur du constructeur pour lequel ils sont spécifiés.  Par conséquent, ils peuvent utiliser les noms de paramètres du constructeur.  
  
## Noms globaux  
 Un nom d'objet, de fonction ou d'énumérateur est global s'il est placé en dehors de toute fonction ou classe ou préfixé par l'opérateur de portée unaire globale \(`::`\), et s'il n'est pas utilisé conjointement avec l'un des opérateurs binaires suivants :  
  
-   Résolution de portée \(`::`\)  
  
-   Sélection de membres pour les objets et les références \(**.**\)  
  
-   Sélection de membres pour les pointeurs \(**–\>**\)  
  
## Noms qualifiés  
 Les noms utilisés avec l'opérateur binaire de résolution de portée \(`::`\) sont appelés des noms qualifiés. Le nom spécifié après l'opérateur binaire de résolution de portée doit être membre de la classe spécifiée à gauche de l'opérateur ou membre d'une ou plusieurs de ses classes de base.  
  
 Les noms spécifiés après l'opérateur de sélection de membre \(**.** ou **–\>**\) doivent être membres du type de classe de l'objet spécifié à gauche de l'opérateur ou membres d'une ou plusieurs de ses classes de base.  Les noms spécifiés à droite de l'opérateur de sélection de membre \(**–\>**\) peuvent également être des objets d'un autre type de classe si le côté gauche de **–\>** est un objet classe et que la classe définit un opérateur de sélection de membre surchargé \(**–\>**\) qui correspond à un pointeur vers un autre type de classe.  \(Cette disposition est décrite plus en détail dans [Accès aux membres de classe](../cpp/member-access.md).\)  
  
 Le compilateur recherche les noms dans l'ordre suivant et s'arrête après avoir trouvé le nom :  
  
1.  Portée de bloc active si le nom est utilisé dans une fonction. Sinon, portée globale.  
  
2.  Vers l'extérieur dans chaque portée de bloc englobante, notamment la portée de fonction externe \(qui inclut des paramètres de fonction\).  
  
3.  Si le nom est utilisé dans une fonction membre, il est recherché dans la portée de la classe.  
  
4.  Le nom est recherché dans les classes de base de la classe.  
  
5.  La recherche est effectuée dans la portée de classe imbriquée englobante \(le cas échéant\) et ses bases.  La recherche se poursuit jusqu'à atteindre la portée de classe englobante externe.  
  
6.  La recherche est effectuée dans la portée globale.  
  
 Toutefois, vous pouvez apporter des modifications à cet ordre de recherche comme suit :  
  
1.  Les noms précédés de `::` forcent la recherche à commencer au niveau de la portée globale.  
  
2.  Les noms précédés des mots clés **class**, `struct` et **union** forcent le compilateur à rechercher uniquement les noms **class**, `struct` ou **union**.  
  
3.  Les noms à gauche de l'opérateur de résolution de portée \(`::`\) peuvent être uniquement des noms **class**, `struct`, **namespace** ou **union**.  
  
 Si le nom fait référence à un membre non statique mais est utilisé dans une fonction membre statique, un message d'erreur est généré.  De même, si le nom fait référence à un membre non statique d'une classe englobante, un message d'erreur est généré car les classes englobées n'ont pas de pointeurs **this** de classe englobante.  
  
## Noms de paramètres de fonction  
 Les noms de paramètres de fonction dans les définitions de fonction sont considérés comme étant dans la portée du bloc le plus à l'extérieur de la fonction.  Par conséquent, il s'agit de noms régionaux. Ils se trouvent hors de portée lors de la sortie de la fonction.  
  
 Les noms de paramètres de fonction dans les déclarations de fonctions \(prototypes\) sont dans la portée locale de la déclaration et sortent de la portée à la fin de la déclaration.  
  
 Les paramètres par défaut sont dans la portée du paramètre pour lequel ils sont la valeur par défaut, comme décrit dans les deux paragraphes précédents.  Toutefois, ils ne peuvent pas accéder à des variables locales ou à des membres de classes non statiques.  Les paramètres par défaut sont évalués au point de l'appel de fonction, mais ils sont évalués dans la portée d'origine de la déclaration de fonction.  Par conséquent, les paramètres par défaut pour les fonctions membres sont toujours évalués dans la portée de classe.  
  
## Voir aussi  
 [Héritage](../cpp/inheritance-cpp.md)