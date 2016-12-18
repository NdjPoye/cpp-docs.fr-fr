---
title: "fsetpos | Microsoft Docs"
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
  - "fsetpos"
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
  - "fsetpos"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fsetpos (fonction)"
  - "flux, définir les indicateurs de position"
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fsetpos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit l'indicateur de position du flux.  
  
## Syntaxe  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `pos`  
 Stockage de positions indicateur.  
  
## Valeur de retour  
 En cas de réussite, `fsetpos` retourne 0.  En cas d'échec, la fonction retourne une valeur différente de zéro et définit `errno` à l'une des constantes manifestes suivantes \(définies dans ERRNO.H\) : `EBADF`, c'est\-à\-dire que le fichier n'est pas accessible ou que l'objet vers lequel `stream` pointe n'est pas une structure de fichiers valide ; ou `EINVAL`, c'est\-à\-dire qu'une valeur non valide pour `stream` ou `pos` a été passée.  Si un paramètre non valide a été passé, ces fonctions appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes de retour.  
  
## Notes  
 La fonction `fsetpos` définit l'indicateur d'emplacement de fichier pour `stream` à la valeur `pos`*,* qui est obtenue dans l'appel antérieur à `fgetpos` sur `stream`*.* La fonction désactive l'indicateur de fin de fichier et supprime tous les effets de [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) sur `stream`*.* Après avoir appelé `fsetpos`, l'opération suivante sur `stream` peut être soit une entrée soit une sortie.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [fgetpos](../../c-runtime-library/reference/fgetpos.md).  
  
## Équivalent .NET Framework  
 [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)