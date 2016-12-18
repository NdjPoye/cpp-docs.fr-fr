---
title: "Exemple de makefile pour PCH | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
ms.assetid: daf68983-77dc-45db-8701-aa89ad18910d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exemple de makefile pour PCH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le makefile suivant utilise des macros et une structure de commandes de flux de contrôle \!IF, \!ELSE, \!ENDIF pour simplifier son adaptation à votre projet.  
  
```  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
 En dehors des macros STABLEHDRS, BOUNDRY et UNSTABLEHDRS représentées dans la figure « Structure d'un makefile utilisant un fichier d'en\-tête précompilé » dans [Fichiers PCH utilisés dans le processus de génération](../../build/reference/pch-files-in-the-build-process.md), ce makefile fournit une macro CLFLAGS et une macro LINKFLAGS.  Vous devez utiliser ces macros pour répertorier les options du compilateur et de l'éditeur de liens qui s'appliquent aussi bien à la génération d'une version Debug qu'à la génération d'une version finale du fichier exécutable de l'application.  Il existe également une macro LIBS dans laquelle vous recensez les bibliothèques dont votre projet a besoin.  
  
 Le makefile utilise également \!IF, \!ELSE, \!ENDIF afin de déterminer si vous définissez un symbole DEBUG sur la ligne de commande NMAKE :  
  
```  
NMAKE DEBUG=[1|0]  
```  
  
 Cette fonctionnalité permet d'utiliser le même makefile pendant le développement et pour les versions finales de votre programme ; utilisez DEBUG\=0 pour les versions finales.  Les lignes de commande suivantes sont équivalentes :  
  
```  
NMAKE   
NMAKE DEBUG=0  
```  
  
 Pour plus d'informations sur les makefiles, consultez [Référence NMAKE](../../build/nmake-reference.md).  Consultez également [Options du compilateur](../../build/reference/compiler-options.md) et [Options de l'éditeur de liens](../../build/reference/linker-options.md).  
  
## Voir aussi  
 [Utilisation d'en\-têtes précompilés dans un projet](../../build/reference/using-precompiled-headers-in-a-project.md)