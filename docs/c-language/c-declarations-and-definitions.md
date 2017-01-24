---
title: "D&#233;clarations et d&#233;finitions C | Microsoft Docs"
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
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;clarations et d&#233;finitions C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une déclaration établit une association entre une variable, une fonction ou un type particulier et ses attributs.  [Vue d'ensemble des déclarations](../c-language/overview-of-declarations.md) donne la syntaxe ANSI pour le non terminal `declaration`.  Une déclaration spécifie également où et quand un identificateur est accessible \(liaison d'un identificateur\).  Consultez [Durée de vie, portée, visibilité, et liaison](../c-language/lifetime-scope-visibility-and-linkage.md) pour plus d'informations sur la liaison.  
  
 Une définition d'une variable établit les mêmes associations qu'une déclaration mais génère également un stockage à allouer pour la variable.  
  
 Par exemple, les fonctions `main`, `find` et `count` et les variables `var` et `val` sont définies dans un fichier source dans l'ordre suivant :  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 Les variables `var` et `val` peuvent être utilisées dans les fonctions `find` et `count`. Aucune autre déclaration n'est requise.  Mais ces noms ne sont pas visibles \(sont inaccessibles\) dans `main`.  
  
## Voir aussi  
 [Fichiers sources et programmes sources](../c-language/source-files-and-source-programs.md)