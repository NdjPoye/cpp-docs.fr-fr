---
title: "_close | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_close"
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
  - "_close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_close (fonction)"
  - "close (fonction)"
  - "fichiers (C++), fermer"
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ferme un fichier.  
  
## Syntaxe  
  
```  
int _close(   
   int fd   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
## Valeur de retour  
 `_close` retourne 0 si le fichier a été fermée.  Une valeur de retour de \-1 indique une erreur.  
  
## Notes  
 La fonction `_close` ferme le fichier associé à `fd`.  
  
 Le descripteur de fichier et le descripteur de fichier sous\-jacent du système d'exploitation sont fermés.  Par conséquent, il n'est pas nécessaire d'appeler `CloseHandle` si le fichier a été ouvert à l'aide de la fonction Win32`CreateFile` et a été converti en un descripteur de fichier en utilisant `_open_osfhandle`.  
  
 Cette fonction valide ses paramètres.  Si `fd` est un mauvais descripteur de fichier, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'execution est autorisée à se poursuivre, la fonction retourne \-1 et `errno` est fixé à `EBADF`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_close`|\<io.h,\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple pour[open](../../c-runtime-library/reference/open-wopen.md).  
  
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_unlink, \_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)