---
title: "_strdate_s, _wstrdate_s | Microsoft Docs"
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
  - "_strdate_s"
  - "_wstrdate_s"
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
  - "_strdate_s"
  - "wstrdate_s"
  - "_wstrdate_s"
  - "strdate_s"
  - "_tstrdate_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "dates, copie"
  - "tstrdate_s, fonction"
  - "wstrdate_s, fonction"
  - "_tstrdate_s, fonction"
  - "strdate_s, fonction"
  - "copier les dates"
  - "_strdate_s, fonction"
  - "_wstrdate_s, fonction"
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdate_s, _wstrdate_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copiez la date système actuelle vers une mémoire tampon.  Il s'agit de versions de [](../../c-runtime-library/reference/strdate-wstrdate.md "_strdate, _wstrdate")[Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `buffer`  
 Un pointeur vers une mémoire tampon qui sera rempli avec la chaine de dates formatée.  
  
 \[in\] `numberOfElements`  
 Taille de la mémoire tampon.  
  
## Valeur de retour  
 Zéro en cas de réussite.  La valeur de retour est un code d'erreur en cas de échec.  Les codes d'erreur sont définis dans ERRNO.H ; consultez le tableau ci\-dessous pour les erreurs exactes générées par cette fonction.  Pour plus d'informations sur les codes d'erreur, consultez [errno](../../c-runtime-library/errno-constants.md).  
  
## Conditions d'erreur  
  
|`buffer`|`numberOfElements`|Return|Contenu de `buffer`.|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|\(Indifférent\)|`EINVAL`|Non modifié|  
|Non `NULL` \(pointeur vers la mémoire tampon valide\)|0|`EINVAL`|Non modifié|  
|Non `NULL` \(pointeur vers la mémoire tampon valide\)|0 \< `numberOfElements` \< 9|`EINVAL`|Chaîne vide|  
|Non `NULL` \(pointeur vers la mémoire tampon valide\)|`numberOfElements` \>\= 9|0|Date du jour au format spécifié dans les notes|  
  
## Problèmes de sécurité  
 Transmettre des valeurs non valides non`NULL` du tampon génère une violation d'accès si le paramètre`numberOfElements` est supérieur à 9.  
  
 Passer des valeurs pour une taille supérieure à la taille réelle de`buffer` entraîne un dépassement de mémoire tampon.  
  
## Notes  
 Ces fonctions fournissent des versions plus sécurisées de`_strdate` et de`_wstrdate`.  La fonction `_strdate_s` copie la date système actuelle vers la mémoire tampon désignée par le`buffer`, `mm`mis en forme\/`dd`\/`yy`, où les deux chiffres `mm` représentent le mois, les chiffres `dd` représentent le jour, et les deux chiffres`yy`sont les deux derniers chiffres de l'année.  Par exemple, la chaîne `12/05/99` représente le le 5 décembre 1999.  La mémoire tampon doit contenir au moins 9 caractères.  
  
 `_wstrdate_s` est une version caractères larges de `_strdate_s`; l'argument et la valeur de retour de  `_wstrdate_s` sont des chaînes de caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
 Si `buffer` est un pointeur `NULL`, ou si `numberOfElements` est inférieur à 9 caractères, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'execution peut se poursuivre, ces fonctions retournent \-1 et définissent`errno` à `EINVAL` si la mémoire tampon est `NULL` ou si `numberOfElements` est inférieure ou égal à 0, ou définissent `errno` à `ERANGE` si `numberOfElements` est inférieur à 9.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappage de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h\> or \<wchar.h\>|  
|`_strdate_s`|\<time.h\>|  
  
## Exemple  
 Consultez l'exemple de [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## Équivalent .NET Framework  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)