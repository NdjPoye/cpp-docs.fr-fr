---
title: "strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs"
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
  - "strftime"
  - "_wcsftime_l"
  - "_strftime_l"
  - "wcsftime"
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
  - "_tcsftime"
  - "strftime"
  - "wcsftime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strftime_l (fonction)"
  - "strftime (fonction)"
  - "tcsftime (fonction)"
  - "_wcsftime_l (fonction)"
  - "wcsftime (fonction)"
  - "_tcsftime (fonction)"
  - "chaînes heure"
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strftime, wcsftime, _strftime_l, _wcsftime_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Formate une chaîne de temps.  
  
## Syntaxe  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `strDest`  
 Chaîne de sortie.  
  
 `maxsize`  
 Taille de la mémoire tampon `strDest`, mesurée en caractères \(`char` ou `wchart_t`\).  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `timeptr`  
 `tm` structure de données  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `strftime` retourne le nombre de caractères placés dans `strDest` et `wcsftime` retourne le nombre correspondant de caractères larges.  
  
 Si le nombre total de caractères, y compris le NULL de fin, est supérieure à `maxsize`, `strftime` et `wcsftime` retournent 0 et le contenu de `strDest` est indéterminé.  
  
 Le nombre de caractères dans `strDest` est égal au nombre de caractères littéraux dans `format` ainsi que tous les caractères qui peuvent être ajoutés à `format` via les codes de mise en forme.  Le null de fin d'une chaîne n'est pas comptabilisé dans la valeur de retour.  
  
## Notes  
 Les fonctions `strftime` et `wcsftime` mettent en forme la valeur de temps `tm` dans `timeptr` selon l'argument fourni `format` et stockent le résultat dans la mémoire tampon `strDest`*.* Tout au plus, les caractères `maxsize` se trouvent dans la chaîne.  Pour obtenir une description des champs dans la structure `timeptr`, consultez [asctime](../../c-runtime-library/reference/asctime-wasctime.md).  `wcsftime` est l'équivalent en caractères larges de `strftime`; son argument de pointeur de chaîne pointe vers une chaîne de caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
> [!NOTE]
>  Dans les versions antérieures à Visual C\+\+ 2005, la documentation a décrit le paramètre `format` de `wcsftime` comme ayant le type de données `const wchar_t *`, mais l'implémentation réelle du type de données `format` est `const char *`.  L'implémentation du type de donnéesd' `format`a été mise à jour pour refléter la documentation précédente et active, c. \- à\-d., `const wchar_t *`.  
  
 Cette fonction valide ses paramètres.  Si `strDest`, `format`, ou`timeptr` est un pointeur null, ou si la structure de données `tm` adressée par `timeptr` est non valide \(par exemple, s'il contient des valeurs hors limites pour l'heure et la date\), ou si la chaîne `format` contient le code de mise en forme valide, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne 0 et définit `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 L'argument `format` consiste en un ou plusieurs codes ; comme dans `printf`, les codes de mise en forme sont précédés d'un symbole de pourcentage \(`%`\).  Les caractères qui ne commencent pas par `%` sont copiés sans changement sur `strDest`*.* La catégorie `LC_TIME` des paramètres régionaux actuels affecte le format de sortie de `strftime`. \(Pour plus d'informations sur `LC_TIME`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).\) Les fonctions sans le suffixe `_l` utilisent les paramètres locaux actuellement définis.  Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles prennent les paramètres régionaux comme paramètre et les utilisent au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 les codes de mise en forme pour `strftime` sont répertoriées ci\-dessous :  
  
 `%a`  
 Nom abrégé du jour de la semaine  
  
 `%A`  
 Nom complet du jour de la semaine  
  
 `%b`  
 Nom du mois abrégé  
  
 `%B`  
 Nom complet du mois  
  
 `%c`  
 Représentation de date et d'heure appropriée pour les paramètres régionaux  
  
 `%d`  
 Jour du mois en nombre décimal \(01 – 31\)  
  
 `%H`  
 Heure au format 24 heures \(00 à 23\)  
  
 `%I`  
 Heure au format 12 heures \(01 à 12\)  
  
 `%j`  
 Jour de l'année sous la forme d'un nombre décimal \(001 – 366\)  
  
 `%m`  
 Mois sous la forme d'un nombre décimal \(01 – 12\)  
  
 `%M`  
 Minutes sous la forme d'un nombre décimal \(00 – 59\)  
  
 `%p`  
 Indicateur A.M.\/P.M. \(matin\/après\-midi\) des paramètres régionaux actuels pour une horloge de 12 heures  
  
 `%S`  
 Deuxième en nombre décimal \(00 – 59\)  
  
 `%U`  
 Semaine de l'année sous la forme d'un nombre décimal, avec dimanche en tant que premier jour de la semaine \(00 à 53\)  
  
 `%w`  
 Jour de la semaine en nombre décimal \(0 à 6 ; Dimanche est 0\)  
  
 `%W`  
 Semaine de l'année sous la forme d'un nombre décimal, avec lundi en tant que premier jour de la semaine \(00 à 53\)  
  
 `%x`  
 Représentation de date pour les paramètres régionaux actuels  
  
 `%X`  
 Représentation d'heure pour les paramètres régionaux actuels  
  
 `%y`  
 Année sans siècle, en nombre décimal \(00 – 99\)  
  
 `%Y`  
 Année avec siècle, en nombre décimal  
  
 `%z, %Z`  
 Le nom du fuseau horaire ou abréviation de fuseau horaire, en fonction de les paramètres du Registre ; pas de caractères si le fuseau horaire est inconnu  
  
 `%%`  
 Pourcentage  
  
 Comme dans la fonction `printf`, l'indicateur `#` peut précéder n'importe quel code de mise en forme.  Dans ce cas, la signification du code de format est modifiée comme suit.  
  
|Code du format|Signification|  
|--------------------|-------------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|L'indicateur `#` est ignoré.|  
|`%#c`|Représentation longue de la date et de l'heure, appropriée pour les paramètres régionaux actuels.  Par exemple : " Mardi 14 mars 1995, 12:41:29"|  
|`%#x`|Représentation longue de la date, appropriée aux paramètres régionaux actuels.  Par exemple : " Mardi 14 mars 1995"|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|Supprimer des zéros initiaux \(le cas échéant\).|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strftime`|\<time.h\>|  
|`wcsftime`|\<time.h\> or \<wchar.h\>|  
|`_strftime_l`|\<time.h\>|  
|`_wcsftime_l`|\<time.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## Équivalent .NET Framework  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)