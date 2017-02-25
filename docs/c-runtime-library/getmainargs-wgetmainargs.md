---
title: "__getmainargs, __wgetmainargs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__wgetmainargs"
  - "__getmainargs"
apilocation: 
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# __getmainargs, __wgetmainargs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelle l'analyse de ligne de commande et copie les arguments dans `main()` à travers les pointeurs passés.  
  
## Syntaxe  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### Paramètres  
 `_Argc`  
 Unentier qui contient le nombre d'arguments qui suivent dans `argv`.  Le paramètre `argc` est toujours supérieur ou égal à 1.  
  
 `_Argv`  
 Tableau de chaînes terminées par le caractère NULL qui représentent les arguments de ligne de commande entrés par l'utilisateur du programme.  Par convention, `argv[0]`est la commande avec laquelle le programme est appelé, argv\[1\] est le premier argument de ligne de commande, et ainsi de suite, jusqu'à argv\[argc\], qui est toujours NULL.  Le premier argument de ligne de commande est toujours `argv[1]` et le dernier est `argv[argc – 1]`.  
  
 `_Env`  
 Il s'agit d'un tableau de chaînes représentant les variables définies dans l'environnement de l'utilisateur.  Ce tableau se termine par une entrée NULL.  
  
 `_DoWildCard`  
 Un entier qui si il est défini à la valeur 1 développe les caractères génériques dans les arguments de ligne de commande, ou si il est défini à la valeur 0 n'a aucun effet.  
  
 `_StartInfo`  
 D'autres informations à transmettre à la dll CRT.  
  
## Valeur de retour  
 0 en cas de réussite ; une valeur négative en cas d'échec.  
  
## Notes  
 Utilisez `__getmainargs` sur les plateformes de caractères non larges, et `__wgetmainargs` sur les plateformes de caractères larges \(Unicode\).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_\_getmainargs|internal.h|  
|\_\_wgetmainargs|internal.h|