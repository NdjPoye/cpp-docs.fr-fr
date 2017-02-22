---
title: "_get_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_fmode"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_fmode"
  - "_get_fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_fmode (fonction)"
  - "translation de fichier (C++), mode par défaut"
  - "get_fmode (fonction)"
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _get_fmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Va chercher le mode de traduction du fichier par défaut pour les opérations E\/S du fichier.  
  
## Syntaxe  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### Paramètres  
 \[out\] `pmode`  
 Pointeur vers un entier à remplir avec le mode par défaut actuel : `_O_TEXT` ou `_O_BINARY`.  
  
## Valeur de retour  
 Retourne zéro si l'opération a réussi ; un code d'erreur en cas de échec.  Si`pmode`est `NULL`, le gestionnaire de paramètres invalide est appelé comme décrit dans[Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini comme `EINVAL` et la fonction retourne `EINVAL`.  
  
## Notes  
 La fonction obtient la valeur de la variable globale [\_fmode](../../c-runtime-library/fmode.md).  Cette variable spécifie le mode de fichier de traduction pour les opérations de bas niveau et de flux de données d'E\/S, telles que `_open`, `_pipe`, `fopen`, et `freopen`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_get_fmode`|\<stdlib.h\>|\<fcntl.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md).  
  
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_fmode](../../c-runtime-library/fmode.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [E\/S de fichier en mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md)