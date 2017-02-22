---
title: "fseek, _fseeki64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fseeki64"
  - "fseek"
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
apitype: "DLLExport"
f1_keywords: 
  - "fseek"
  - "_fseeki64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fseeki64 (fonction)"
  - "pointeurs de fichier (C++)"
  - "pointeurs de fichier (C++), déplacer"
  - "fseek (fonction)"
  - "fseeki64 (fonction)"
  - "rechercher des pointeurs de fichier"
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# fseek, _fseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déplace le pointeur de fichier vers un emplacement spécifié.  
  
## Syntaxe  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `offset`  
 Nombre d'octets de `origin`.  
  
 `origin`  
 Position initiale.  
  
## Valeur de retour  
 En cas de succès `fseek` et `_fseeki64` retourne 0.  Sinon, il retourne une valeur différente de zéro.  Sur des périphériques incapables d'effectuer des recherches, la valeur de retour n'est pas définie.  Si `stream` est un pointeur null, ou si `origin` n'est pas l'une des valeurs autorisées décrites ci\-dessous, `fseek` et `_fseeki64` appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1.  
  
## Notes  
 Les fonctions`fseek` et `_fseeki64` déplacent le pointeur de fichier \(s'il existe\) associé à `stream` vers un nouvel emplacement qui est décalé de`offset` octets par rapport à l'`origin`*.* L'opération suivante dans le flux de donnée prend place dans le nouvel emplacement.  Dans un flux ouvert pour la mise à jour, l'opération suivante peut être soit une lecture soit ou une écriture.  L'origine de l'argument doit etre l'une des constantes suivantes, définies dans STDIO.H :  
  
 `SEEK_CUR`  
 Position actuelle du pointeur de fichier.  
  
 `SEEK_END`  
 Fin du fichier.  
  
 `SEEK_SET`  
 Début du fichier.  
  
 Vous pouvez utiliser `fseek` et `_fseeki64` pour repositionner le pointeur n'importe ou dans un fichier.  Le pointeur peut également être placé au delà de la fin du fichier.  `fseek` et `_fseeki64`nettoie l'indicateur de fin de fichier et inverse le résultat de tous les appels antérieurs `ungetc` sur `stream`.  
  
 Lorsqu'un fichier est ouvert pour ajouter des données, la position actuelle du fichier est déterminée par la dernière opération d'E\/S, et non par lorsque l'écriture suivante se produirait.  Si aucune opération d'E\/S ne s'est produite dans un fichier ouvert pour l'ajout, la position de fichier correspond au début du fichier.  
  
 Pour les flux de données ouverts en mode texte, `fseek` et `_fseeki64`ont une utilisation limitée, car les traductions de saut de ligne\-retour de chariot peuvent faire que`fseek` et `_fseeki64`produisent des résultats inattendus.  Les seules opérations`fseek` et `_fseeki64`, qui sont assurées d'utiliser des flux de données ouverts en mode texte sont :  
  
-   Recherchant un décalage de 0 par rapport à n'importe laquelle des valeurs d'origine.  
  
-   Recherchant du début du fichier avec une valeur de décalage retournée par un appel à `ftell` en utilisant `fseek`ou `_ftelli64`en utilisant`_fseeki64`.  
  
 Dans le mode texte, CTRL\+Z est interprété comme un caractère de fin de fichier en entrée.  Dans les fichiers ouverts pour lecture\/écriture  `fopen`et toutes les autres routines vérifient la présence de Ctrl\+Z à la fin du fichier et le supprime si possible.  Cette opération est effectuée car l'utilisation de la combinaison de `fseek` et de `ftell`ou`_fseeki64` et `_ftelli64`, pour se déplacer à l'intérieur d'un fichier , qui se termine par un CTRL\+Z peut agir sur`fseek` ou`_fseeki64`et provoquer leur comportement de manière inappropriée près de la fin du fichier.  
  
 Lorsque le CRT ouvre un fichier qui commence par une marque d'ordre d'octet \(BOM\), dle pointeur du fichier est positionné après le BOM \(qui est, au commencement du vrai contenu d'un fichier\)  Si vous devez `fseek` au début du fichier, utilisez `ftell` pour obtenir la position initiale et `fseek`le plutôt que pour la position 0.  
  
 Cette fonction verrouille d'autres threads pendant l'exécution et est par conséquent thread\-safe.  Pour une version non verrouillante, consultez [\_fseek\_nolock, \_fseeki64\_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fseek`|\<stdio.h\>|  
|`_fseeki64`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
  **Le pointeur de fichier est défini au milieu de la première ligne.**  
**Il s'agit du fichier « fseek.out ».**   
## Équivalent .NET Framework  
  
-   [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
-   [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)