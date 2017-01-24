---
title: "Utilisation des symboles C ou C++ dans les blocs __asm | Microsoft Docs"
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
  - "__asm (mot clé) (C++), éléments de C/C++ dans"
  - "__asm (mot clé) (C++), syntaxe"
  - "symboles, in __asm (blocs)"
  - "Visual C, symbols in __asm (blocs)"
  - "Visual C++, in __asm (blocs)"
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Utilisation des symboles C ou C++ dans les blocs __asm
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Spécifique à Microsoft  
 Un  `__asm`bloc peut faire référence à n'importe quel symbole de C ou C\+\+ dans la portée dans laquelle le bloc apparaît.  \(Symboles C et C\+\+ sont des noms de variables, des noms de fonction et des étiquettes ; Autrement dit, les noms qui ne sont pas des constantes symboliques ou  `enum`membres.  Vous ne pouvez pas appeler membres C\+\+ fonctions.\)  
  
 Certaines restrictions s'appliquent à l'utilisation de symboles C et C\+\+ :  
  
-   Chaque instruction de langage d'assemblage peut contenir uniquement un seul C ou le symbole de C\+\+.  Plusieurs symboles peuvent apparaître dans la même instruction assembly uniquement avec  **longueur**,  **TYPE de**, et  **taille** expressions.  
  
-   Les fonctions référencées dans une  `__asm`bloc doit être déclaré \(prototypée\) plus haut dans le programme.  Dans le cas contraire, le compilateur ne peut pas faire la distinction entre les noms de fonction et des étiquettes de la  `__asm`bloc.  
  
-   Un  `__asm`bloc ne peut pas utiliser de symboles C ou C\+\+ avec la même orthographe en tant que mots réservé de MASM \(indépendamment de la casse\).  Mots réservé de MASM incluent les noms des instructions telles que  **PUSH** et d'enregistrer des noms comme SI.  
  
-   Balises de structure et d'union ne sont pas reconnues dans  `__asm`blocs.  
  
 **FIN spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation de C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)