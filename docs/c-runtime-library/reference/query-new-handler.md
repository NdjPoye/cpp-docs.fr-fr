---
title: "_query_new_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_handler"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_query_new_handler"
  - "query_new_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_query_new_handler (fonction)"
  - "gestion des erreurs"
  - "routines du gestionnaire"
  - "query_new_handler (fonction)"
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _query_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne l'adresse de la routine du nouveau gestionnaire actuel.  
  
## Syntaxe  
  
```  
  
      _PNH _query_new_handler(  
   void   
);  
```  
  
## Valeur de retour  
 Retourne l'adresse de la routine du nouveau gestionnaire actuel, comme défini par `_set_new_handler`.  
  
## Notes  
 La fonction C\+\+ `_query_new_handler` retourne l'adresse de la fonction actuelle gérant les exceptions définie par la fonction C\+\+ [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md).  `_set_new_handler` est utilisé pour spécifier une fonction de gestion des exceptions qui est à même de gagner du contrôle si l'opérateur **new** échoue dans l'allocation de mémoire.  Pour plus d'informations, consultez des discussions des fonctions [opérateur nouveau](../../misc/operator-new-function.md) et [suppression d'opérateur](../../misc/operator-delete-function.md) dans le *Guide de référence du langage C\+\+*.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_query_new_handler`|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)