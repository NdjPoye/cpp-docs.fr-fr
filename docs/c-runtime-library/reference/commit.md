---
title: "_commit | Microsoft Docs"
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
  - "_commit"
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
  - "_commit"
  - "commit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_commit (fonction)"
  - "commit (fonction)"
  - "valider les fichiers sur un disque"
  - "fichiers (C++), vider"
  - "vider les fichiers sur un disque"
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _commit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vide un fichier directement sur le disque.  
  
## Syntaxe  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
## Valeur de retour  
 `_commit` retourne 0 si le fichier a été vidé sur le disque avec succès.  Une valeur de retour de \-1 indique une erreur.  
  
## Notes  
 La fonction `_commit` force le système d'exploitation à écrire le fichier associé à `fd` sur le disque.  Cet appel s'assure que le fichier spécifié soit vidé immédiatement, et non à la discretion du système d'exploitation.  
  
 Si `fd` a la valeur NULL, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  If execution is allowed to continue, the function returns \-1 and `errno` is set to `EBADF`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`_commit`|\<io.h,\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_read](../../c-runtime-library/reference/read.md)   
 [\_write](../../c-runtime-library/reference/write.md)