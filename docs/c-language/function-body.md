---
title: "Corps de fonction | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "corps de fonction"
  - "définitions de fonction, corps de fonction"
  - "fonctions (C), syntaxe"
  - "variables, syntaxe des fonctions"
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Corps de fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un « corps de fonction » est une instruction composée contenant les instructions qui spécifient ce que fait la fonction.  
  
## Syntaxe  
 *function\-definition* :  
 *declaration\-specifiers*  opt *attribute\-seq* opt *declarator declaration\-list* opt *compound\-statement*  
  
 \/\* *attribute\-seq* est spécifique à Microsoft \*\/  
  
 *compound\-statement* : \/\* Le corps de la fonction \*\/  
 **{**  *declaration\-list*  opt *statement\-list* opt **}**  
  
 Les variables déclarées dans un corps de fonction, appelées « variables locales », ont une classe de stockage **auto** sauf indication contraire.  Lorsque la fonction est appelée, du stockage est créé pour les variables locales et les initialisations locales sont exécutées.  Le contrôle d'exécution passe à la première instruction dans *compound\-statement* et continue jusqu'à ce qu'une instruction `return` soit exécutée ou jusqu'à la fin du corps de la fonction.  Le contrôle revient ensuite au point auquel la fonction a été appelée.  
  
 Une instruction `return` contenant une expression doit être exécutée si la fonction doit retourner une valeur.  La valeur de retour d'une fonction est non définie si aucune instruction `return` n'est exécutée ou si l'instruction `return` n'inclut pas d'expression.  
  
## Voir aussi  
 [Définitions de fonction C](../c-language/c-function-definitions.md)