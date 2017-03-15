---
title: "Commentaires dans un makefile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "makefiles, commentaires"
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Commentaires dans un makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Faites précéder un commentaire du signe dièse \(\#\).  NMAKE ignore le texte compris entre le dièse et le caractère de saut de ligne suivant.  Exemples :  
  
```  
# Comment on line by itself  
OPTIONS = /MAP  # Comment on macro definition line  
  
all.exe : one.obj two.obj  # Comment on dependency line  
    link one.obj two.obj  
# Comment in commands block  
#   copy *.obj \objects  # Command turned into comment  
    copy one.exe \release  
  
.obj.exe:  # Comment on inference rule line  
    link $<  
  
my.exe : my.obj ; link my.obj  # Err: cannot comment this  
 # Error: # must be the first character  
.obj.exe: ; link $<  # Error: cannot comment this  
```  
  
 Pour spécifier un dièse littéral, faites\-le précéder du signe insertion \(**^**\), comme suit :  
  
```  
DEF = ^#define  #Macro for a C preprocessing directive  
```  
  
## Voir aussi  
 [Contenu d'un makefile](../build/contents-of-a-makefile.md)