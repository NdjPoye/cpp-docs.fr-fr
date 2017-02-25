---
title: "ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64_s"
  - "_wctime32_s"
  - "ctime_s"
  - "_wctime64_s"
  - "_ctime32_s"
  - "_wctime_s"
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
  - "ctime64_s"
  - "_ctime32_s"
  - "_tctime32_s"
  - "_ctime64_s"
  - "_wctime_s"
  - "_tctime_s"
  - "_tctime64_s"
  - "ctime_s"
  - "ctime32_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctime32_s, fonction"
  - "ctime64_s, fonction"
  - "_tctime64_s, fonction"
  - "_wctime_s, fonction"
  - "tctime_s, fonction"
  - "_wctime64_s, fonction"
  - "ctime_s, fonction"
  - " ctime32_s, fonction"
  - "_ctime64_s, fonction"
  - "tctime64_s, fonction"
  - "wctime64_s, fonction"
  - "wctime_s, fonction"
  - "_tctime_s, fonction"
  - "tctime32_s, fonction"
  - "wctime32_s, fonction"
  - "heure, convertir"
  - "_ctime32_s, fonction"
  - "_tctime32_s, fonction"
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir une valeur d’heure en une chaîne et ajuster les paramètres de fuseau horaire local. Voici les versions de [ctime, \_ctime64, \_wctime, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) avec des améliorations de sécurité comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `buffer`  
 Doit être suffisamment grande pour contenir les 26 caractères. Un pointeur vers le résultat de chaîne de caractères, ou `NULL`si :  
  
-   `time` représente une date antérieure au 1er janvier 1970 à minuit UTC.  
  
-   Si vous utilisez `_ctime32_s` ou `_wctime32_s` et `time` représente une date postérieure à 23:59:59 18 janvier 2038, UTC.  
  
-   Si vous utilisez `_ctime64_s` ou `_wctime64_s` et `time` représente une date postérieure à 23:59:59 le 31 décembre 3000, UTC.  
  
-   Si vous utilisez `_ctime_s` ou `_wctime_s`, ces fonctions sont des wrappers pour les fonctions précédentes. Consultez la section Notes.  
  
 \[in\] `numberOfElements`  
 Taille de la mémoire tampon.  
  
 \[in\] t`ime`  
 Pointeur vers l’heure stockée.  
  
## Valeur de retour  
 Zéro si l’opération réussit. S’il existe un échec en raison d’un paramètre non valide, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, un code d’erreur est retourné. Codes d’erreur sont définis dans ERRNO. H ; Pour obtenir la liste de ces erreurs, consultez la page [errno](../../c-runtime-library/errno-constants.md). Les codes d’erreur levées pour chaque condition d’erreur sont affichés dans le tableau suivant.  
  
## Conditions d’erreur  
  
|`buffer`|`numberOfElements`|`time`|Retourner|Valeur de `buffer`|  
|--------------|------------------------|------------|---------------|------------------------|  
|`NULL`|any|any|`EINVAL`|Non modifié|  
|Pas `NULL` \(pointe vers la mémoire valide\)|0|any|`EINVAL`|Non modifié|  
|Pas `NULL`|0 \< taille \< 26|any|`EINVAL`|Chaîne vide|  
|Pas `NULL`|\>\= 26|NULL|`EINVAL`|Chaîne vide|  
|Pas `NULL`|\>\= 26|\< 0|`EINVAL`|Chaîne vide|  
  
## Notes  
 Le `ctime_s` fonction convertit une valeur d’heure stockée en tant qu’un [time\_t](../../c-runtime-library/standard-types.md) structure dans une chaîne de caractères. Le `time` valeur est généralement obtenue à partir d’un appel à [temps](../../c-runtime-library/reference/time-time32-time64.md), qui retourne le nombre de secondes écoulé depuis minuit \(00 : 00:00\), le 1er janvier 1970, temps universel \(UTC\). La chaîne de valeur de retour contient exactement 26 caractères et présente sous la forme :  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Une horloge de 24 heures est utilisée. Tous les champs ont une largeur constante. Le caractère de nouvelle ligne \('\\n'\) et le caractère null \('\\0'\) occupent les deux dernières positions de la chaîne.  
  
 La chaîne de caractères convertie est également ajustée en fonction des paramètres de fuseau horaire local. Consultez le `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), et [localtime32\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) fonctions pour plus d’informations sur la configuration de l’heure locale et la [\_tzset](../../c-runtime-library/reference/tzset.md) \(fonction\) pour plus d’informations sur la définition de l’environnement de fuseau horaire et des variables globales.  
  
 `_wctime32_s` et `_wctime64_s` sont la version à caractères larges de `_ctime32_s` et `_ctime64_s`qui retourne un pointeur vers une chaîne à caractères larges. Dans le cas contraire, `_ctime64_s`, `_wctime32_s`, et `_wctime64_s` se comportent de la même manière que `_ctime32_s`.  
  
 `ctime_s` est une fonction inline qui prend la valeur `_ctime64_s` et `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t` comme ancien `time_t` 32 bits, vous pouvez définir `_USE_32BIT_TIME_T`. Cette action provoquerait `ctime_s` pour prendre la valeur `_ctime32_s`. Cela est déconseillé, car votre application peut échouer après le 18 janvier 2038, et il n’est pas autorisée sur les plateformes 64 bits.  
  
 En C\+\+, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument taille. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`ctime_s,`<br /><br /> `_ctime32_s,`<br /><br /> `_ctime64_s`|\<time.h\>|  
|`_wctime_s,`<br /><br /> `_wctime32_s,`<br /><br /> `_wctime64_s`|\< time.h \> ou \< wchar.h \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## Résultat de l'exemple  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## Équivalent .NET Framework  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)