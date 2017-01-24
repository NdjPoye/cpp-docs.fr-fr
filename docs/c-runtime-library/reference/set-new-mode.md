---
title: "_set_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_new_mode"
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
  - "set_new_mode"
  - "_set_new_mode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_new_mode (fonction)"
  - "modes de gestionnaire"
  - "set_new_mode (fonction)"
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un nouveau mode gestionnaire pour `malloc`.  
  
## Syntaxe  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### Paramètres  
 `newhandlermode`  
 Nouveau mode gestionnaire pour `malloc`; la valeur valide est 0 ou 1.  
  
## Valeur de retour  
 Retourne le mode précédent du gestionnaire défini pour `malloc`.  Une valeur de retour de 1 indique que, en cas de échec d'allocation de mémoire, `malloc` a appelé précédement la nouvelle routine du gestionnaire ; une valeur de retour de 0 indique que ce n'est pas le cas.  Si l'argument `newhandlermode` n'est pas égal à 0 ou 1, il retourne – 1.  
  
## Notes  
 La fonction C\+\+ `_set_new_mode` définit le nouveau mode du gestionnaire de [malloc](../../c-runtime-library/reference/malloc.md).  Le nouveau mode de gestionnaire indique si, en cas de échec, `malloc` doit appeler la nouvelle routine du gestionnaire comme définit par [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md).  Par défaut, `malloc` n'appelle pas la nouvelle routine de gestionnaire en cas de défaillance pour allouer de la mémoire.  Vous pouvez substituer ce comportement par défaut afin que, lorsque `malloc` ne réussit pas à allouer la mémoire, `malloc` appelle la nouvelle routine de gestionnaire de la même manière que l'opérateur `new` lorsqu'il échoue pour la même raison.  Pour plus d'informations, consultez les opérateurs [new](../../cpp/new-operator-cpp.md) et [delete](../../cpp/delete-operator-cpp.md) dans le *Guide de référence du langage C\+\+*.  Pour substituer la valeur par défaut, appelez:  
  
```  
_set_new_mode(1)  
```  
  
 tôt dans votre programme, ou lié avec NEWMODE.OBJ \(consultez [Options de lien](../../c-runtime-library/link-options.md)\).  
  
 Cette fonction valide son paramètre.  Si `newhandlermode` est quelque chose d'autre que 0 ou 1, la fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, , **\_**`set_new_mode` retourne \-1 et fixe `errno` à `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_new_mode`|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [\_query\_new\_mode](../../c-runtime-library/reference/query-new-mode.md)