---
title: "_open, _wopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_open"
  - "_wopen"
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
  - "_wopen"
  - "_topen"
  - "_open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_open (fonction)"
  - "_topen (fonction)"
  - "_wopen (fonction)"
  - "fichiers (C++), ouvrir"
  - "open (fonction)"
  - "ouvrir des fichiers, pour E/S de fichier"
  - "topen (fonction)"
  - "wopen (fonction)"
ms.assetid: 13f6a0c3-d1aa-450d-a7aa-74abc91b163e
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# _open, _wopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ouvre un fichier.  Ces fonctions sont déconseillées, car des versions plus sécurisées sont disponibles ; consultez [\_sopen\_s, \_wsopen\_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## Syntaxe  
  
```  
int _open(  
   const char *filename,  
   int oflag [,  
   int pmode]   
);  
int _wopen(  
   const wchar_t *filename,  
   int oflag [,  
   int pmode]   
);  
```  
  
#### Paramètres  
 `filename`  
 Nom du fichier.  
  
 `oflag`  
 Type d'opérations autorisées.  
  
 `pmode`  
 Mode d'autorisation.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne un descripteur de fichier pour le fichier ouvert.  La valeur de retour \-1 indique une erreur ; dans ce cas, `errno` prend l'une des valeurs suivantes.  
  
 `EACCES`  
 A essayé d'ouvrir un fichier en lecture seule pour un accès en écriture, le mode de partage du fichier n'autorise pas les opérations spécifiées ou le chemin d'accès donné est un répertoire.  
  
 `EEXIST`  
 Indicateurs `_O_CREAT` et `_O_EXCL` spécifiés, mais `filename` existe déjà.  
  
 `EINVAL`  
 Argument `oflag` ou `pmode` non valide.  
  
 `EMFILE`  
 Plus aucun descripteur de fichier n'est disponible \(trop de fichiers sont ouverts\).  
  
 `ENOENT`  
 Fichier ou chemin d'accès introuvable.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_open` ouvre le fichier spécifié par `filename` et le prépare pour la lecture ou l'écriture, comme spécifié par `oflag`.  `_wopen` est une version à caractères larges de `_open` ; l'argument `filename` de `_wopen` est une chaîne à caractères larges.  Sinon, `_wopen` et `_open` se comportent de la même façon.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_topen`|`_open`|`_open`|`_wopen`|  
  
 `oflag` est une expression d'entier formée à partir d'une ou plusieurs des constantes manifestes ou combinaisons de constantes suivantes, qui sont définies dans \<fcntl.h\>.  
  
 `_O_APPEND`  
 Déplace le pointeur de fichier à la fin du fichier avant chaque opération d'écriture.  
  
 `_O_BINARY`  
 Ouvre le fichier en mode binaire \(non traduit\).  \(Pour obtenir une description du mode binaire, voir [fopen](../../c-runtime-library/reference/fopen-wfopen.md).\)  
  
 `_O_CREAT`  
 Crée un fichier et l'ouvre pour l'accès en écriture.  N'a aucun effet si le fichier spécifié par `filename` existe.  L'argument `pmode` est obligatoire quand `_O_CREAT` est spécifié.  
  
 `_O_CREAT` &#124; `_O_SHORT_LIVED`  
 Crée un fichier temporaire et, dans la mesure du possible, n'effectue pas de vidage sur disque.  L'argument `pmode` est obligatoire quand `_O_CREAT` est spécifié.  
  
 `_O_CREAT` &#124; `_O_TEMPORARY`  
 Crée un fichier temporaire ; le fichier est supprimé quand le dernier descripteur de fichier est fermé.  L'argument `pmode` est obligatoire quand `_O_CREAT` est spécifié.  
  
 `_O_CREAT` &#124; `_O_EXCL`  
 Retourne une valeur d'erreur si le fichier spécifié par `filename` existe.  Applicable uniquement en cas d'utilisation avec `_O_CREAT`.  
  
 `_O_NOINHERIT`  
 Empêche la création d'un descripteur de fichier partagé.  
  
 `_O_RANDOM`  
 Indique que la mise en cache est optimisée pour, mais non limitée à, l'accès aléatoire à partir du disque.  
  
 `_O_RDONLY`  
 Ouvre un fichier pour l'accès en lecture uniquement.  Ne peut pas être spécifié avec `_O_RDWR` ou `_O_WRONLY`.  
  
 `_O_RDWR`  
 Ouvre le fichier pour l'accès en lecture et en écriture.  Ne peut pas être spécifié avec `_O_RDONLY` ou `_O_WRONLY`.  
  
 `_O_SEQUENTIAL`  
 Indique que la mise en cache est optimisée pour, mais non limitée à, l'accès séquentiel à partir du disque.  
  
 `_O_TEXT`  
 Ouvre un fichier en mode texte \(traduit\).  \(Pour plus d'informations, voir [E\/S de fichier en mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md) et [fopen](../../c-runtime-library/reference/fopen-wfopen.md).\)  
  
 `_O_TRUNC`  
 Ouvre un fichier et le tronque à une longueur nulle. Le fichier doit disposer d'une autorisation en écriture.  Ne peut pas être spécifié avec `_O_RDONLY`.  `_O_TRUNC` utilisé avec `_O_CREAT` ouvre un fichier existant ou crée un fichier.  
  
> [!NOTE]
>  L'indicateur `_O_TRUNC` détruit le contenu du fichier spécifié.  
  
 `_O_WRONLY`  
 Ouvre le fichier pour l'accès en écriture uniquement.  Ne peut pas être spécifié avec `_O_RDONLY` ou `_O_RDWR`.  
  
 `_O_U16TEXT`  
 Ouvre le fichier en mode Unicode UTF\-16.  
  
 `_O_U8TEXT`  
 Ouvre le fichier en mode Unicode UTF\-8.  
  
 `_O_WTEXT`  
 Ouvre le fichier en mode Unicode.  
  
 Pour spécifier le mode d'accès au fichier, vous devez spécifier `_O_RDONLY`, `_O_RDWR` ou `_O_WRONLY`.  Il n'y a aucune valeur par défaut pour le mode d'accès.  
  
 Si `_O_WTEXT` est utilisé pour ouvrir un fichier pour l'accès en lecture, `_open` lit le début du fichier et recherche une marque d'ordre d'octet.  S'il en existe une, le fichier est considéré comme étant au format UTF\-8 ou UTF\-16LE, selon la marque d'ordre d'octet.  Dans le cas contraire, le fichier est considéré comme étant au format ANSI.  Quand un fichier est ouvert pour l'accès en écriture à l'aide de `_O_WTEXT`, UTF\-16 est utilisé.  Quel que soit le paramètre précédent ou la marque d'ordre d'octet, si `_O_U8TEXT` est utilisé, le fichier est toujours ouvert en UTF\-8 ; si `_O_U16TEXT` est utilisé, le fichier est toujours ouvert en UTF\-16.  
  
 Quand un fichier est ouvert en mode Unicode à l'aide de `_O_WTEXT`, `_O_U8TEXT` ou `_O_U16TEXT`, les fonctions d'entrée traduisent les données lues à partir du fichier en données UTF\-16 stockées comme type `wchar_t`.  Les fonctions qui écrivent dans un fichier ouvert en mode Unicode attendent des mémoires tampons qui contiennent des données UTF\-16 stockées comme type `wchar_t`.  Si le fichier est encodé au format UTF\-8, les données UTF\-16 sont traduites en UTF\-8 lors de leur écriture et le contenu du fichier encodé au format UTF\-8 est traduit en UTF\-16 lorsqu'il est lu.  Toute tentative de lecture ou d'écriture d'une quantité impaire d'octets en mode Unicode provoque une erreur de validation de paramètre.  Pour lire ou écrire des données stockées dans votre programme au format UTF\-8, utilisez un mode de fichier binaire ou texte au lieu d'un mode Unicode.  Vous êtes responsable de toute traduction d'encodage nécessaire.  
  
 Si `_open` est appelée avec `_O_WRONLY|_O_APPEND` \(mode Append\) et `_O_WTEXT`, `_O_U16TEXT` ou `_O_U8TEXT`, elle tente d'abord d'ouvrir le fichier pour la lecture et l'écriture, de lire la marque BOM, puis de le rouvrir pour l'accès en écriture uniquement.  Si l'ouverture du fichier pour l'accès en lecture et en écriture échoue, elle ouvre le fichier pour l'accès en écriture uniquement et utilise la valeur par défaut pour le paramètre de mode Unicode.  
  
 Quand plusieurs constantes manifestes sont utilisées pour former l'argument `oflag`, les constantes sont combinées avec l'opérateur OR au niveau du bit \(                       `|` \).  Pour en savoir plus sur les modes binaire et texte, voir [E\/S de fichier en mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 L'argument `pmode` est obligatoire uniquement quand `_O_CREAT` est spécifié.  Si le fichier existe déjà, `pmode` est ignoré.  Sinon, `pmode` spécifie les paramètres d'autorisation du fichier, qui sont définis quand le nouveau fichier est fermé pour la première fois.  `_open` applique le masque d'autorisation de fichier actif à `pmode` avant que les autorisations soient définies.  \(Pour plus d'informations, voir [\_umask](../../c-runtime-library/reference/umask.md).\) `pmode` est une expression d'entier qui contient l'une des constantes manifestes suivantes ou les deux, qui sont définies dans \<sys\\stat.h\>.  
  
 `_S_IREAD`  
 Lecture autorisée uniquement.  
  
 `_S_IWRITE`  
 Écriture autorisée.  \(En fait, autorise la lecture et l'écriture.\)  
  
 `_S_IREAD`  `|`  `_S_IWRITE`  
 Lecture et écriture autorisées.  
  
 Quand les deux constantes sont données, elles sont jointes avec l'opérateur OR au niveau du bit \(                       `|` \).  Dans Windows, tous les fichiers sont lisibles ; l'autorisation d'écriture seule n'est pas disponible.  Ainsi, les modes `_S_IWRITE` et `_S_IREAD` `|` `_S_IWRITE` sont équivalents.  
  
 Si la valeur spécifiée pour `pmode` est différente d'une combinaison de `_S_IREAD` et `_S_IWRITE` \(même si elle spécifie un `pmode` valide dans un autre système d'exploitation\) ou si elle se différencie des valeurs `oflag` autorisées, la fonction génère une assertion en mode débogage et appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne \-1 et définit `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_open`|\<io.h\>|\<fcntl.h\>, \<sys\\types.h\>, \<sys\\stat.h\>|  
|`_wopen`|\<io.h\> ou \<wchar.h\>|\<fcntl.h\>, \<sys\\types.h\>, \<sys\\stat.h\>|  
  
 `_open` et `_wopen` sont des extensions Microsoft.  Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_open.c  
// compile with: /W3  
/* This program uses _open to open a file  
 * named CRT_OPEN.C for input and a file named CRT_OPEN.OUT  
 * for output. The files are then closed.  
 */  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int fh1, fh2;  
  
   fh1 = _open( "CRT_OPEN.C", _O_RDONLY ); // C4996  
   // Note: _open is deprecated; consider using _sopen_s instead  
   if( fh1 == -1 )  
      perror( "Open failed on input file" );  
   else  
   {  
      printf( "Open succeeded on input file\n" );  
      _close( fh1 );  
   }  
  
   fh2 = _open( "CRT_OPEN.OUT", _O_WRONLY | _O_CREAT, _S_IREAD |   
                            _S_IWRITE ); // C4996  
   if( fh2 == -1 )  
      perror( "Open failed on output file" );  
   else  
   {  
      printf( "Open succeeded on output file\n" );  
      _close( fh2 );  
   }  
}  
```  
  
## Sortie  
  
```  
Open succeeded on input file  
Open succeeded on output file  
```  
  
## Équivalent .NET Framework  
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
-   <xref:System.IO.FileStream.%23ctor%2A>  
  
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)