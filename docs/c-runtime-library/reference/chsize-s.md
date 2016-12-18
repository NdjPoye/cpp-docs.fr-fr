---
title: "_chsize_s | Microsoft Docs"
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
  - "_chsize_s"
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
  - "chsize_s"
  - "_chsize_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chsize_s (fonction)"
  - "chsize_s (fonction)"
  - "fichiers (C++), modifier la taille"
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chsize_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Changes the size of a file.  Il s'agit de versions de [](../../c-runtime-library/reference/chsize.md "_chsize")[Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
 `size`  
 Longueur du fichier en octets.  
  
## Valeur de retour  
 `_chsize_s`  retourne la valeur 0 si la taille du fichier a été modifiée.  Une valeur de retour de – 1 indique une erreur : la valeur retournée est `EACCES`  si le fichier spécifié est verrouillé contre tout accès, `EBADF`  si le fichier spécifié est en lecture seule ou si l'un des descripteurs est invalide, `ENOSPC`  si aucun espace ne reste sur le périphérique,ou `EINVAL`  si la taille est inférieure à 0.  `errno` est définie à la meme valeur.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_chsize_s`  étend ou tronque le fichier associé à `fd` à la longueur spécifiée par `size`.  Le fichier doit être ouvert dans un mode qui permet d'écrire.  Les caractères Null \("\\0 "\) sont ajoutés si le fichier est étendu.  Si le fichier est tronqué, toutes les données de la fin du fichier original raccourci sont perdues.  
  
 `_chsize_s` prend un entier 64 bits comme taille de fichier, et peut donc gérer des tailles de fichier plus grande que 4 Gigas.  `_chsize` est limité aux tailles de fichier 32 bits.  
  
 Cette fonction valide ses paramètres.  Si `fd` n'est pas un descripteur de fichier valide ou si la taille est inférieure à zéro, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_chsize_s`|\<io.h,\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)