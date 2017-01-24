---
title: "Directives #ifdef et #ifndef (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#ifndef"
  - "#ifdef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#ifdef (directive)"
  - "#ifndef (directive)"
  - "directive ifdef (#ifdef)"
  - "directive ifndef (#ifndef)"
  - "préprocesseur, directives"
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives #ifdef et #ifndef (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les directives **\#ifdef** et **\#ifndef** effectuent la même tâche que la directive `#if` lorsqu'elle est utilisée avec **defined**\( *identifier* \).  
  
## Syntaxe  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## Notes  
 Vous pouvez utiliser les directives **\#ifdef** et **\#ifndef** partout où la directive `#if` peut être utilisée.  L'instruction **\#ifdef** *identifier* est équivalente à `#if 1` lorsque *identifier* a été défini, et à `#if 0` lorsque *identifier* n'a pas été défini ou lorsque sa définition a été supprimée avec la directive `#undef`.  Ces directives vérifient uniquement la présence ou l'absence d'identificateurs définis avec `#define`, et non d'identificateurs déclarés dans le code source C ou C\+\+.  
  
 Ces directives sont fournies uniquement pour des raisons de compatibilité avec les versions antérieures du langage.  L'expression constante **defined\(** *identifier* **\)** utilisée avec la directive `#if` est recommandée.  
  
 La directive **\#ifndef** vérifie l'inverse de la condition vérifiée par **\#ifdef**.  Si l'identificateur n'a pas été défini \(ou si sa définition a été supprimée avec `#undef`\), la condition est vraie \(non nulle\).  Sinon, la condition n'est pas vérifiée \(0\).  
  
 **Section spécifique à Microsoft**  
  
 *identifier* peut être passé à partir de la ligne de commande à l'aide de l'option \/D.  Jusqu'à 30 macros peuvent être spécifiées avec \/D.  
  
 Cela est utile pour vérifier si une définition existe, car une définition peut être transmise à partir de la ligne de commande.  Par exemple :  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)