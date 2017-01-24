---
title: "fclose, _fcloseall | Microsoft Docs"
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
  - "fclose"
  - "_fcloseall"
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
  - "fclose"
  - "_fcloseall"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fclose, fonction"
  - "flux, fermer"
  - "_fcloseall, fonction"
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fclose, _fcloseall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ferme un flux de données \(`fclose`\) ou ferme les flux de données ouverts \(`_fcloseall`\).  
  
## Syntaxe  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 `fclose` retourne 0 si le flux a été fermé avec succès.  `_fcloseall` retourne le nombre total de flux de données fermé.  Les deux fonctions retournent`EOF` pour indiquer une erreur.  
  
## Notes  
 La fonction `fclose` ferme `stream`.  Si `stream` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `fclose` renvoie 0 et attribue à `errno` la valeur `EINVAL`.  Il est recommandé que le pointeur `stream` soit toujours vérifié avant d'appeler cette fonction.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
 La fonction `_fcloseall` ferme les flux de données au ouverts à `stdin`, `stdout`, `stderr` \(et, dans MS\-DOS, `_stdaux` et `_stdprn`\).  Elle ferme et supprime également tous les fichiers temporaires créés par `tmpfile`.  Dans les deux fonctions, tous les tampons associés au flux sont détruits avant de fermer.  Les tampons alloué au système sont libérées lorsque le flux de données est fermé.  Les mémoires tampons affectées par l'utilisateur avec `setbuf` et `setvbuf` ne sont pas automatiquement libérées.  
  
 **Note:** lorsque ces fonctions sont utilisées pour fermer un flux de données, le descripteur de fichier sous\-jacent et le descripteur de fichier du système d'exploitation \(ou le socket\) sont fermés, ainsi que le flux de données.  Par conséquent, si le fichier a été ouvert en tant que gestionnaire de fichier ou descripteur de fichier et est fermé avec `fclose`, n'appelez pas `_close` pour fermer le descripteur de fichier ; n'appelez pas la fonction `CloseHandle` Win32 pour fermer le descripteur de fichier.  
  
 `fclose` et `_fcloseall` contiennent le code pour se protéger de toute interférence des autres threads.  Pour une version non verrouillante, consultez `fclose`, voir `_fclose_nolock`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fclose`|\<stdio.h\>|  
|`_fcloseall`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple pour[fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## Équivalent .NET Framework  
  
-   [System::IO::BinaryReader::Close](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.close.aspx)  
  
-   [System::IO::BinaryWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.close.aspx)  
  
-   [System::IO::StringReader::Close](https://msdn.microsoft.com/en-us/library/system.io.stringreader.close.aspx)  
  
-   [System::IO::StringWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.stringwriter.close.aspx)  
  
-   [System::IO::Stream::Close](https://msdn.microsoft.com/en-us/library/system.io.stream.close.aspx)  
  
-   [System::IO::StreamReader::Close](https://msdn.microsoft.com/en-us/library/system.io.streamreader.close.aspx)  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.close.aspx)  
  
-   [System::IO::TextReader::Close](https://msdn.microsoft.com/en-us/library/system.io.textreader.close.aspx)  
  
-   [System::IO::TextWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.textwriter.close.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)