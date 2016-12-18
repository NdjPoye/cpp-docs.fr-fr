---
title: "Probl&#232;mes courants de migration vers Visual&#160;C++ 64 bits | Microsoft Docs"
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
  - "portage de code 32 bits (C++)"
  - "applications 64 bits (C++)"
  - "compilateur 64 bits (C++), migration"
  - "compilateur 64 bits (C++), portage de code 32 bits"
  - "programmation 64 bits (C++), migration"
  - "migration (C++), code 64 bits (problèmes)"
  - "portage du code 32 bits vers du code 64 bits"
  - "mettre à niveau les applications Visual C++, code 32 bits"
  - "Win64 (C++)"
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Probl&#232;mes courants de migration vers Visual&#160;C++ 64 bits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous utilisez Visual C\+\+ pour créer des applications destinées à s'exécuter sur un système d'exploitation Windows 64 bits, tenez compte des points suivants :  
  
-   `int` et `long` sont des valeurs 32 bits sur les systèmes d'exploitation Windows 64 bits.  Pour les programmes que vous prévoyez de compiler pour des plateformes 64 bits, veillez à ne pas assigner de pointeurs à des variables 32 bits.  Les pointeurs sont des valeurs 64 bits sur les plateformes 64 bits et vous tronquerez la valeur d'un pointeur si vous l'assignez à une variable 32 bits.  
  
-   `size_t`, `time_t` et  `ptrdiff_t` sont des valeurs 64 bits sur les systèmes d'exploitation Windows 64 bits.  
  
-   `time_t` est une valeur 32 bits sur les systèmes d'exploitation Windows 32 bits dans les versions de Visual C\+\+ antérieures à Visual C\+\+ 2005.  `time_t` est maintenant un entier 64 bits par défaut.  Pour plus d'informations, consultez [Gestion du temps](../c-runtime-library/time-management.md).  
  
     Vous devez savoir dans quels cas votre code prend une valeur `int` et la traite comme une valeur `size_t` ou `time_t`.  En effet, le nombre peut augmenter au point de dépasser la taille d'un nombre 32 bits. Dans ce cas, les données sont tronquées quand elles sont renvoyées vers le stockage `int`.  
  
 Le modificateur %x \(format `int` hexadécimal\) `printf` ne fonctionne pas comme prévu sur un système d'exploitation Windows 64 bits.  Il ne fonctionne que sur les 32 premiers bits de la valeur qui lui est passée.  
  
-   Utilisez %I32x pour afficher un type intégral 32 bits au format hexadécimal.  
  
-   Utilisez %I64x pour afficher un type intégral 64 bits au format hexadécimal.  
  
-   Le %p \(format hexadécimal pour un pointeur\) fonctionnera comme prévu sur un système d'exploitation Windows 64 bits.  
  
 Pour plus d'informations, voir :  
  
-   [Options du compilateur](../build/reference/compiler-options.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="8228b16e9fef41dbba1af1d78bf0cc87" class\="tgtSentence"\>Conseils de migration\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/aa384214)  
  
## Voir aussi  
 [Configuration des programmes pour les processeurs 64 bits](../build/configuring-programs-for-64-bit-visual-cpp.md)   
 [Portage de programmes](http://msdn.microsoft.com/fr-fr/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)