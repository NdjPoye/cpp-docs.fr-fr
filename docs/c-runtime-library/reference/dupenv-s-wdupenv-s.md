---
title: "_dupenv_s, _wdupenv_s | Microsoft Docs"
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
  - "_dupenv_s"
  - "_wdupenv_s"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "tdupenv_s"
  - "_dupenv_s"
  - "wdupenv_s"
  - "dupenv_s"
  - "_tdupenv_s"
  - "_wdupenv_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_dupenv_s (fonction)"
  - "_tdupenv_s (fonction)"
  - "_wdupenv_s (fonction)"
  - "dupenv_s (fonction)"
  - "variables d'environnement"
  - "tdupenv_s (fonction)"
  - "wdupenv_s (fonction)"
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _dupenv_s, _wdupenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient une valeur à partir de l'environnement actuel.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _dupenv_s(    char **buffer,    size_t *numberOfElements,    const char *varname ); errno_t _wdupenv_s(    wchar_t **buffer,    size_t *numberOfElements,    const wchar_t *varname );  
```  
  
#### Paramètres  
 `buffer`  
 Mémoire tampon pour stocker la valeur de la variable.  
  
 `numberOfElements`  
 Taille de la `buffer`.  
  
 `varname`  
 Nom de la variable d'environnement.  
  
## Valeur de retour  
 Zéro en cas de réussite, code d'erreur en cas d'échec.  
  
 Ces fonctions valident leurs paramètres ; si `buffer` ou `varname` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, les fonctions affectent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
 Si ces fonctions ne peuvent pas allouer suffisamment de mémoire, elles affectent à `buffer` la valeur `NULL` et à `numberOfElements` la valeur 0, et retournent `ENOMEM`.  
  
## Notes  
 La fonction `_dupenv_s` recherche `varname` dans la liste des variables d'environnement.  Si la variable est trouvée, `_dupenv_s` alloue une mémoire tampon et copie la valeur de la variable dans la mémoire tampon.  L'adresse et la longueur de la mémoire tampon sont retournées dans `buffer` et `numberOfElements`.  En allouant la mémoire tampon elle\-même, `_dupenv_s` offre une alternative plus pratique à [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!NOTE]
>  Il revient au programme appelant de libérer la mémoire en appelant [free](../../c-runtime-library/reference/free.md).  
  
 Si la variable est introuvable, `buffer` a la valeur `NULL`, `numberOfElements` a la valeur 0, et la valeur de retour est 0, car cette situation n'est pas considérée comme étant une condition d'erreur.  
  
 Si la taille de la mémoire tampon ne vous intéresse pas, vous pouvez affecter `NULL` à `numberOfElements`.  
  
 `_dupenv_s` ne respecte pas la casse dans le système d'exploitation Windows.  `_dupenv_s` utilise la copie de l'environnement vers lequel la variable globale `_environ` pointe pour accéder à l'environnement.  Voir la section Notes dans [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md) pour plus d'informations sur `_environ`.  
  
 La valeur dans `buffer` est une copie de la valeur de la variable d'environnement ; sa modification n'a aucun impact sur l'environnement.  Utilisez la fonction [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md) pour modifier la valeur d'une variable d'environnement.  
  
 `_wdupenv_s` est une version à caractères larges de `_dupenv_s` ; les arguments de `_wdupenv_s` sont des chaînes à caractères larges.  La variable globale `_wenviron` est une version à caractères larges de `_environ`.  Voir la section Notes dans [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md) pour plus d'informations sur `_wenviron`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tdupenv_s`|`_dupenv_s`|`_dupenv_s`|`_wdupenv_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_dupenv_s`|\<stdlib.h\>|  
|`_wdupenv_s`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_dupenv_s.c  
#include  <stdlib.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## Résultat de l'exemple  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## Équivalent .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [Constantes d'environnement](../../c-runtime-library/environmental-constants.md)   
 [\_dupenv\_s\_dbg, \_wdupenv\_s\_dbg](../../c-runtime-library/reference/dupenv-s-dbg-wdupenv-s-dbg.md)   
 [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)