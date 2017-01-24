---
title: "__thiscall | Microsoft Docs"
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
  - "__thiscall"
  - "__thiscall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__thiscall (mot clé) (C++)"
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __thiscall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Spécifique à Microsoft  
 La convention d'appel `__thiscall` est utilisé sur les fonctions membres et est la convention d'appel par défaut utilisée par les fonctions membres C\+\+ qui n'utilisent pas d'arguments variables.  Sous `__thiscall`, l'appelé nettoie la pile, ce qui est impossible pour les fonctions `vararg`.  Les arguments sont l'objet d'un push sur la pile de droite à gauche, avec le pointeur `this` passé via le registre ECX, et non sur la pile, dans l'architecture x86.  
  
 Une raison d'utiliser `__thiscall` est dans les classes dont les fonctions membres utilisent `__clrcall` par défaut.  Dans ce cas, vous pouvez utiliser `__thiscall` pour rendre différentes fonctions membres appelables depuis le code natif.  
  
 Lors de la compilation avec [\/clr:pure](../build/reference/clr-common-language-runtime-compilation.md), toutes les fonctions et pointeurs fonction sont `__clrcall` sauf indication contraire.  
  
 Dans les versions antérieures à Visual C\+\+ 2005, la convention d'appel de thiscall ne pouvait pas être spécifiée explicitement dans un programme, car `thiscall` n'était pas un mot clé.  
  
 Les fonctions membres `vararg` utilisent la convention d'appel `__cdecl`.  Tous les arguments de fonction font l'objet d'un push sur la pile, le pointeur d' `this` étant placé sur le bout de pile  
  
 Puisque cette convention d'appel s'applique uniquement à C\+\+, il n'existe aucun modèle de nom de décoration C.  
  
 Pour les ordinateurs ARM et les ordinateurs [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)], `__thiscall` est accepté et ignoré par le compilateur.  
  
 Pour les fonctions de classe non statiques, si la fonction est définie hors ligne, il n'est pas nécessaire de spécifier le modificateur de convention d'appel dans la définition hors ligne.  En d'autres termes, pour les méthodes membres non statiques de classe, la convention d'appel spécifiée pendant la déclaration est prise par défaut au point de définition.  
  
## Exemple  
  
```  
// thiscall_cc.cpp  
// compile with: /c /clr:oldSyntax  
struct CMyClass {  
   void __thiscall mymethod();  
   void __clrcall mymethod2();  
};  
```  
  
## END Spécifique à Microsoft  
  
## Voir aussi  
 [Passage des arguments et conventions de dénomination](../cpp/argument-passing-and-naming-conventions.md)