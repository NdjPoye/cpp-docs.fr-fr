---
title: "Substitution macro | Microsoft Docs"
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
  - "macros, NMAKE"
  - "programme NMAKE, substitution macro"
  - "substitutions macros dans NMAKE"
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Substitution macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque *macroname* est appelé, chaque occurrence de *string1* est remplacée dans sa chaîne de définition par *string2*.  
  
## Syntaxe  
  
```  
$(macroname:string1=string2)  
```  
  
## Remarques  
 La substitution macro tient compte de la casse et est littérale ; *string1* et *string2* ne peuvent pas appeler des macros.  La substitution ne modifie pas la définition d'origine.  Vous pouvez substituer du texte dans n'importe quelle macro prédéfinie, sauf [$$@](../build/filename-macros.md).  
  
 Le point\-virgule ne peut pas être précédé par des espaces et des tabulations ; sinon, ceux\-ci sont considérés comme des caractères littéraux.  Si *string2* est nulle, toutes les occurrences de *string1* sont supprimées de la chaîne de définition de la macro.  
  
## Voir aussi  
 [Utilisation d'une macro NMAKE](../build/using-an-nmake-macro.md)