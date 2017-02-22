---
title: "_umask | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_umask"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_umask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_umask (fonction)"
  - "autorisations fichier (C++)"
  - "fichiers (C++), paramètres des autorisations pour"
  - "masques"
  - "masques, paramètre des autorisations fichier"
  - "umask (fonction)"
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _umask
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit le masque d'accès de fichier par défaut.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_umask\_s](../../c-runtime-library/reference/umask-s.md).  
  
## Syntaxe  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### Paramètres  
 `pmode`  
 Paramètre d'autorisation par défaut.  
  
## Valeur de retour  
 `_umask` retourne la valeur précédente de `pmode`.  Aucun retour d'erreur.  
  
## Notes  
 La fonction `_umask` définit le masque d'autorisation du processus actuel comme le mode spécifié par `pmode`*.* Le masque des autorisations de fichiers modifie le paramètre d'autorisation des nouveaux fichiers créés par `_creat`, `_open`, ou `_sopen`.  Si un bit dans le masque est 1, le bit correspondant dans la valeur requise d'autorisation du fichier est défini à 0 \(pas autorisé\).  Si un bit dans le masque est 0, le bit correspondant est inchangé.  Le paramètre d'autorisation pour un nouveau fichier n'est pas défini tant que le fichier n'a pas été fermé pour la première fois.  
  
 L'expression entière `pmode` contient une des deux ou les deux constantes manifestes suivantes, défini dans SYS\\STAT.H :  
  
 `_S_IWRITE`  
 Écriture autorisée.  
  
 `_S_IREAD`  
 Lecture autorisée.  
  
 `_S_IREAD | _S_IWRITE`  
 Lecture et écriture autorisées.  
  
 Lorsque les deux constantes sont fournies, elles sont jointes à l'opérateur de bits OR \(          `|`  \).  Si l'argument `pmode` est `_S_IREAD`, la lecture n'est pas autorisée \(le fichier est en écriture seule.  Si l'argument `pmode` est `_S_IWRITE`, l'écriture n'est pas autorisée \(le fichier est en lecture seule\).  Par exemple, si le bit d'écriture est défini dans le masque, tous les nouveaux fichiers sont en lecture seule.  Notez que avec MS\-DOS et des systèmes d'exploitation Windows, tous les fichiers sont lisibles ; il est impossible de donner l'autorisation en écriture seule.  Par conséquent, définir le bit de lecture avec `_umask` n'a aucun effet sur les modes du fichier.  
  
 Si `pmode` n'est pas une combinaison de l'une des constantes manifestes ou n'incorpore pas un jeu de remplacement de constantes, la fonction ignore simplement celles\-ci.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_umask`|\<io.h\>, \<sys\/stat.h\>, \<sys\/types.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
  **Oldmask \= 0x0000**   
## Équivalent .NET Framework  
 [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)