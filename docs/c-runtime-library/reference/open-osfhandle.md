---
title: "_open_osfhandle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_open_osfhandle"
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
  - "_open_osfhandle"
  - "open_osfhandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "open_osfhandle, fonction"
  - "descripteurs de fichiers [C++], associer"
  - "_open_osfhandle, fonction"
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _open_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Associer un descripteur de fichier run time C au fichier existant de manipulation du système d'exploitation.  
  
## Syntaxe  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### Paramètres  
 `osfhandle`  
 Fichier de système d'exploitation géré.  
  
 `flags`  
 Types d'opérations autorisées.  
  
## Valeur de retour  
 En cas de réussite, `_open_osfhandle` retourne le descripteur d'exécution en cours c.  Sinon, il retourne \-1.  
  
## Notes  
 La fonction `_open_osfhandle` alloue un descripteur d'exécution en cours en C et l'associe au descripteur de fichier du système d'exploitation spécifié par `osfhandle`.  L'argument `flags` est une expression entière formée d'au moins l'une des constantes explicites définies dans Fcntl.h.  Lorsque plus de deux constantes manifestes sont utilisées pour former l'argument `flags`, les constantes sont combinées avec l'opérateur de bits OR \(  **&#124;** \).  
  
 Fcntl.h définit les constantes manifestes suivantes.  
  
 **\_O\_APPEND**  
 Place un pointeur de fichier à la fin du fichier avant chaque opération d'écriture.  
  
 **\_O\_RDONLY**  
 Ouvre le fichier en lecture seule.  
  
 **\_O\_TEXT**  
 Ouvre le fichier en mode texte \(traduit\).  
  
 **\_O\_WTEXT**  
 Ouvre le fichier en mode Unicode \(traduit UTF\-16\).  
  
 Pour fermer un fichier ouvert avec `_open_osfhandle`, appelez `_close`.  Le descripteur sous\-jacent est également fermée par un appel à `_close`, il n'est pas nécessaire d'appeler la fonction Win32 `CloseHandle` sur le descripteur d'origine.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_open_osfhandle`|\<io.h,\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)