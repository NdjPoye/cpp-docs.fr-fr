---
title: "toupper, _toupper, towupper, _toupper_l, _towupper_l | Microsoft Docs"
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
  - "_toupper_l"
  - "towupper"
  - "toupper"
  - "_towupper_l"
  - "_toupper"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "towupper"
  - "_toupper"
  - "_totupper"
  - "toupper"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_totupper (fonction)"
  - "_toupper (fonction)"
  - "_toupper_l (fonction)"
  - "_towupper_l (fonction)"
  - "casse, convertir"
  - "caractères, convertir"
  - "conversion de chaînes, casse"
  - "conversion de chaînes, en caractères différents"
  - "totupper (fonction)"
  - "toupper (fonction)"
  - "toupper_l (fonction)"
  - "towupper (fonction)"
  - "towupper_l (fonction)"
  - "majuscules, convertir les chaînes en"
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# toupper, _toupper, towupper, _toupper_l, _towupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertie des caractères en majuscules.  
  
## Syntaxe  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à convertir.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces routines convertit une copie de`c`, si possible, puis retourne le résultat.  
  
 Si `c` est un caractère large pour lequel `iswlower` est différente de zéro et qu'il y a un caractère large correspondant pour lequel `iswupper` est différente de zéro, `towupper` retourne le caractère large correspondant ; sinon, `towupper` retourne`c` inchangé.  
  
 Aucune valeur de retour n'est réservée pour indiquer une erreur.  
  
 Pour que `toupper` montre les résultats attendus, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) et [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) doivent tous les deux retourner une valeur non nulle.  
  
## Notes  
 Chacune de ces routines convertit une lettre minuscule donnée en un caractère majuscule lorsque cela est possible et approprié.  La conversion en majuscules ou minuscules de`towupper` est spécifique aux paramètres locaux.  Seuls les caractères concernant les paramètres locaux actuels sont modifiés en cas de.  Les fonctions sans le suffixe `_l` utilisent les paramètres locaux actuellement définis.  Les versions de ces fonctions avec le suffixe `_l`  sont identiques, sauf qu'elles utilisent les paramètres locaux passés au lieu des paramètres locaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Pour que `toupper` montre les résultats attendus, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) et [islower](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) doivent tous les deux retourner une valeur non nulle.  
  
 [routines de conversion de données](../../c-runtime-library/data-conversion.md)  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  `_toupper_l` et `_towupper_l` n'ont aucune dépendance de paramètres régionaux et ne sont pas censés être appelés directement.  Ils sont fournis pour un usage interne par `_totupper_l`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`toupper`|\<ctype.h\>|  
|`_toupper`|\<ctype.h\>|  
|`towupper`|\<ctype.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple dans [des fonctions](../../c-runtime-library/to-functions.md).  
  
## Équivalent .NET Framework  
 [System::Char::ToUpper](https://msdn.microsoft.com/en-us/library/system.char.toupper.aspx)  
  
## Voir aussi  
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [to, fonctions](../../c-runtime-library/to-functions.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)