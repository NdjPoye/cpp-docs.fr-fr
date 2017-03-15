---
title: "auto, mot cl&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "auto"
  - "auto_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto (mot clé)"
  - "classe de stockage automatique, auto (mot clé)"
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto, mot cl&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `auto` est un spécificateur de déclaration.  Cependant, le code C\+\+ standard définit une signification originale et modifiée pour ce mot clé .  Avant [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)], le mot clé `auto` déclare une variable dans la classe de stockage *automatique* ; c'est\-à\-dire, une variable qui a une durée de vie locale.  À partir de [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)], le mot clé `auto` déclare une variable dont le type est déduit à partir de l'expression d'initialisation de la déclaration.  L'option du compilateur [\/Zc:auto &#91;\-&#93;](../build/reference/zc-auto-deduce-variable-type.md) contrôle la signification du mot clé `auto`.  
  
## Syntaxe  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## Notes  
 La définition du mot clé `auto` change dans le langage de programmation C\+\+, mais pas dans le langage de programmation C.  
  
 Les rubriques suivantes décrivent le mot clé `auto` et l'option du compilateur correspondante :  
  
-   [auto](../cpp/auto-cpp.md) décrit la nouvelle définition du mot clé `auto`.  
  
-   [\(NOTINBUILD\)auto Keyword \(Storage\-Class Specifier\)](http://msdn.microsoft.com/fr-fr/c7d0cecf-393d-4058-a6e6-b39e31d9edb0) décrit la définition d'origine du mot clé `auto`.  
  
-   [\/Zc:auto \(déduire le type de variable\)](../build/reference/zc-auto-deduce-variable-type.md) décrit l'option du compilateur qui indique au compilateur la définition du mot clé `auto` à utiliser.  
  
## Voir aussi  
 [\(NOTINBUILD\)Storage\-Class Specifiers](http://msdn.microsoft.com/fr-fr/10b3d22d-cb40-450b-994b-08cf9a211b6c)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)