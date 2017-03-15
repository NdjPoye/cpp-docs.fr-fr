---
title: "___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___unguarded_readlc_active_add_func"
  - "___setlc_active_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ___setlc_active_func, ___unguarded_readlc_active_add_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OBSOLÈTE.  Le CRT exporte ces fonctions internes uniquement pour préserver la compatibilité binaire.  
  
## Syntaxe  
  
```cpp  
int ___setlc_active_func(void); int * ___unguarded_readlc_active_add_func(void);  
```  
  
## Valeur de retour  
 La valeur retournée n'est pas significative.  
  
## Notes  
 Bien que les fonctions CRT internes `___setlc_active_func` et `___unguarded_readlc_active_add_func` soient obsolètes et plus utilisées, elles sont exportées par la bibliothèque CRT pour préserver la compatibilité binaire.  Le rôle initial de `___setlc_active_func` était de retourner le nombre d'appels actifs à la fonction `setlocale`.  Le rôle initial de `___unguarded_readlc_active_add_func` était de retourner le nombre de fonctions qui référençaient les paramètres locaux sans les verrouiller.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|aucun|  
  
## Voir aussi  
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)