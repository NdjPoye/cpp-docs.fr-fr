---
title: "__dllonexit | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__dllonexit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__dllonexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dllonexit"
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __dllonexit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enregistre une routine à appeler au moment de la sortie.  
  
## Syntaxe  
  
```  
_onexit_t __dllonexit(  
   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### Paramètres  
 `func`  
 Pointeur vers une fonction à exécuter lors de la sortie.  
  
 `pbegin`  
 Pointeur vers une variable qui indique le début d'une liste de fonctions pour exécuter en détaché.  
  
 `pend`  
 Pointeur vers une variable qui indique la fin d'une liste de fonctions pour exécuter en détaché.  
  
## Valeur de retour  
 En cas de réussite, un pointeur vers la fonction de l'utilisateur.  Sinon, un pointeur null.  
  
## Notes  
 La fonction `__dllonexit` est analogue à la fonction [\_onexit](../c-runtime-library/reference/onexit-onexit-m.md) mais les variables globales utilisées par cette fonction ne sont pas visibles pour cette routine.  À la place des variables globales, cette fonction utilise les paramètres `pbegin` et `pend`.  
  
 Les fonctions `_onexit` et `atexit` dans une DLL liée à MSVCRT.LIB doivent conserver leur propre liste d'atexit\/\_onexit.  Cette routine est le processus qui est appelé par de telles DLL.  
  
 Le type `_PVFV` n'est pas défini comme `typedef void (__cdecl *_PVFV)(void)`.  
  
## Configuration requise  
  
|Routine|Fichier obligatoire|  
|-------------|-------------------------|  
|\_\_dllonexit|onexit.c|  
  
## Voir aussi  
 [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)