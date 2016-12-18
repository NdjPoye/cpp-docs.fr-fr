---
title: "_strtime_s, _wstrtime_s | Microsoft Docs"
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
  - "_wstrtime_s"
  - "_strtime_s"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wstrtime_s"
  - "strtime_s"
  - "wstrtime_s"
  - "_strtime_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtime_s (fonction)"
  - "_wstrtime_s (fonction)"
  - "copier des heures dans les mémoires tampons"
  - "strtime_s (fonction)"
  - "heure, copier"
  - "wstrtime_s (fonction)"
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strtime_s, _wstrtime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copiez l'heure  actuelle vers une mémoire tampon.  Il s'agit de versions de [\_strtime, \_wstrtime](../../c-runtime-library/reference/strtime-wstrtime.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _strtime_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrtime_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strtime_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrtime_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `buffer`  
 Une mémoire tampon, d'au moins 10 octets, où le temps sera écrit.  
  
 \[in\] `numberOfElements`  
 Taille de la mémoire tampon.  
  
## Valeur de retour  
 Zéro en cas de réussite.  
  
 Si une erreur advient, le gestionnaire de paramètres invalides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  La valeur de retour est un code d'erreur en cas de échec.  Les codes d'erreur sont définis dans ERRNO.H ; consultez le tableau suivant pour les erreurs exactes générées par cette fonction.  Pour plus d'information sur le codes d'erreur, consultez [errno Constants](../../c-runtime-library/errno-constants.md).  
  
### Conditions d'erreur  
  
|`buffer`|`numberOfElements`|Return|Contenu de `buffer`.|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|\(Indifférent\)|`EINVAL`|Non modifié|  
|Non `NULL` \(pointeur vers la mémoire tampon valide\)|0|`EINVAL`|Non modifié|  
|Non `NULL` \(pointeur vers la mémoire tampon valide\)|0 \< size \< 9|`EINVAL`|Chaîne vide|  
|Non `NULL` \(pointeur vers la mémoire tampon valide\)|Size \> 9|0|Heure actuelle au format spécifié dans les notes|  
  
## Problèmes de sécurité  
 Transmettre dans une valeur non\-NULL invalide pour a mémoire tampon engendrera une violation des droits d'accès si le paramètre \<parameterReference\>numberOfElements\<\/parameterReference\> est plus grand que 9.  
  
 Passer une valeur pour  `numberOfElements` qui est plus grande que la taille actuelle de la mémoire tampon engendrera un dépassement de capacité de la mémoire tampon.  
  
## Notes  
 Ces fonctions fournissent des versions plus sécurisées de`_strtime` et de`_wstrtime`.  La fonction `_strtime_s` copie l'heure locale actuelle dans la mémoire tampon désignée par `timestr`*.* L'heure est mise sous la forme `hh:mm:ss` où `hh` sont deux chiffres qui représentent l'heure dans la notation horaire sur 24 heures, `mm` sont deux chiffres qui représentent les minutes après l'heure, et `ss` sont deux chiffres représentant les secondes.  Par exemple, la chaîne `18:23:44` représente 23 minutes et 44 secondes après 18h La mémoire tampon doit être au moins de 9 octets ; la taille réelle est spécifiée par le deuxième paramètre.  
  
 `_wstrtime` est une version caractères larges de `_strtime`; l'argument et la valeur de retour de  `_wstrtime` sont des chaînes de caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappage de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tstrtime_s`|`_strtime_s`|`_strtime_s`|`_wstrtime_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strtime_s`|\<time.h\>|  
|`_wstrtime_s`|\<time.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// strtime_s.c  
  
#include <time.h>  
#include <stdio.h>  
  
int main()  
{  
    char tmpbuf[9];  
    errno_t err;  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    // Display operating system-style date and time.   
    err = _strtime_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
      exit(1);  
    }  
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );  
    err = _strdate_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );  
  
}  
```  
  
  **Heure du système d'exploitation :            14h37 49s**  
**Date du système d'exploitation : 04\/25\/03**   
## Équivalent .NET Framework  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)