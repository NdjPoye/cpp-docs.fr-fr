---
title: "tolower, _tolower, towlower, _tolower_l, _towlower_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_tolower_l"
  - "towlower"
  - "tolower"
  - "_tolower"
  - "_towlower_l"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_totlower"
  - "tolower"
  - "_tolower"
  - "towlower"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tolower (fonction)"
  - "_tolower_l (fonction)"
  - "_totlower (fonction)"
  - "_towlower_l (fonction)"
  - "casse, convertir"
  - "caractères, convertir"
  - "minuscules, convertir en"
  - "conversion de chaînes, casse"
  - "conversion de chaînes, en caractères différents"
  - "tolower (fonction)"
  - "tolower_l (fonction)"
  - "totlower (fonction)"
  - "towlower (fonction)"
  - "towlower_l (fonction)"
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# tolower, _tolower, towlower, _tolower_l, _towlower_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Converts a character to lowercase.  
  
## Syntaxe  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### Paramètres  
 \[in\] `c`  
 Caractère à convertir.  
  
 \[in\] `locale`  
 Paramètres régionaux à utiliser pour la traduction spécifique aux paramètres régionaux.  
  
## Valeur de retour  
 Chacune de ces routines convertit une copie de `c` en minuscules si la conversion est possible, puis retourne le résultat.  Aucune valeur de retour n'est réservée pour indiquer une erreur.  
  
## Notes  
 Chacune de ces routines convertit une lettre majuscule donnée en une lettre minuscule lorsque cela est possible et adapté.  La conversion en majuscules ou minuscules de`towlower` est spécifique aux paramètres locaux.  Seuls les caractères concernant les paramètres locaux actuels sont modifiés en cas de.  Les fonctions sans le suffixe `_l` utilisent les paramètres locaux actuellement définis.  Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres locaux passés au lieu des paramètres locaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Pour que `_tolower` montre les résultats attendus, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) et [islower](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) doivent tous les deux retourner une valeur non nulle.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
>  `_tolower_l` et `_towlower_l` n'ont aucune dépendance de paramètres régionaux et ne sont pas censés être appelés directement.  Ils sont fournis pour un usage interne par `_totlower_l`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`tolower`|\<ctype.h\>|  
|`_tolower`|\<ctype.h\>|  
|`towlower`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple dans [des fonctions](../../c-runtime-library/to-functions.md).  
  
## Équivalent .NET Framework  
 [System::Char::ToLower](https://msdn.microsoft.com/en-us/library/system.char.tolower.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [to, fonctions](../../c-runtime-library/to-functions.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)