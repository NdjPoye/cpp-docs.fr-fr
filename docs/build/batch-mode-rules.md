---
title: "R&#232;gles en mode batch | Microsoft Docs"
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
  - "règles d'inférence en mode batch dans NMAKE"
  - "règles d'inférence dans NMAKE"
  - "programme NMAKE, règles d'inférence"
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# R&#232;gles en mode batch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 Les règles d'inférence en mode batch prévoient un seul appel de la règle d'inférence quand N commandes sont concernées par cette règle d'inférence.  Sans ces règles d'inférence en mode batch, il faudrait appeler N commandes.  N est le nombre de dépendants qui déclenchent la règle d'inférence.  
  
 Les makefiles contenant des règles d'inférence en mode batch doivent utiliser NMAKE version 1.62 ou ultérieure.  Pour déterminer la version de NMAKE, exécutez la macro \_NMAKE\_VER fournie avec NMAKE version 1.62 ou ultérieure.  Cette macro retourne une chaîne représentant la version du produit C\+\+.  
  
 La seule différence sur le plan de la syntaxe par rapport à la règle d'inférence standard est que la règle d'inférence en mode batch se termine par un double signe deux\-points \(::\).  
  
> [!NOTE]
>  L'outil appelé doit pouvoir gérer des fichiers multiples.  La règle d'inférence en mode batch doit utiliser `$<` comme macro pour accéder aux fichiers dépendants.  
  
 Les règles d'inférence en mode batch peuvent accélérer le processus de génération.  Il est plus rapide de fournir des fichiers au compilateur en batch, car le pilote du compilateur n'est appelé qu'une seule fois.  Par exemple, le compilateur C et C\+\+ est plus performant quand il gère un ensemble de fichiers car il réside alors en mémoire pendant tout le processus.  
  
 L'exemple suivant montre comment utiliser les règles d'inférence en mode batch :  
  
```  
#  
# sample makefile to illustrate batch-mode inference rules  
#  
O = .  
S = .  
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj  
CFLAGS = -nologo  
  
all : $(Objs)  
  
!ifdef NOBatch  
{$S}.cpp{$O}.obj:  
!else  
{$S}.cpp{$O}.obj::  
!endif  
   $(CC) $(CFLAGS) -Fd$O\ -c $<  
  
$(Objs) :  
  
#end of makefile  
```  
  
 NMAKE produit la sortie suivante sans règles d'inférence en mode batch :  
  
```  
E:\tmp> nmake -f test.mak -a NOBatch=1  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
        cl -nologo -Fd.\ -c .\foo1.cpp  
foo1.cpp  
        cl -nologo -Fd.\ -c .\foo2.cpp  
foo2.cpp  
        cl -nologo -Fd.\ -c .\foo3.cpp  
foo3.cpp  
        cl -nologo -Fd.\ -c .\foo4.cpp  
foo4.cpp  
```  
  
 NMAKE génère le résultat suivant avec les règles d'inférence en mode batch :  
  
```  
E:\tmp> nmake -f test.mak -a  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
  
        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp  
foo1.cpp  
foo2.cpp  
foo3.cpp  
foo4.cpp  
Generating Code...  
```  
  
## Voir aussi  
 [Règles d'inférence](../build/inference-rules.md)