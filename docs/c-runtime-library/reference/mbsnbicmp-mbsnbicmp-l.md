---
title: "_mbsnbicmp, _mbsnbicmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbicmp_l"
  - "_mbsnbicmp"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_strnicmp"
  - "_wcsnicmp_l"
  - "_mbsnbicmp"
  - "mbsnbicmp"
  - "mbsnbicmp_l"
  - "_tcsnicmp"
  - "_strnicmp_l"
  - "_tcsnicmp_l"
  - "_wcsnicmp"
  - "_mbsnbicmp_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbicmp (fonction)"
  - "_mbsnbicmp_l (fonction)"
  - "_strnicmp (fonction)"
  - "_strnicmp_l (fonction)"
  - "_tcsnicmp (fonction)"
  - "_tcsnicmp_l (fonction)"
  - "_wcsnicmp (fonction)"
  - "_wcsnicmp_l (fonction)"
  - "mbsnbicmp (fonction)"
  - "mbsnbicmp_l (fonction)"
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbicmp, _mbsnbicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare `n` octets de deux chaînes de caractères multioctets, en ignorant la casse.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### Paramètres  
 `string1, string2`  
 Chaîne terminée par Null à comparer.  
  
 `count`  
 Nombre d'octets à comparer.  
  
## Valeur de retour  
 La valeur de retour indique la relation entre les sous\-chaînes.  
  
|Valeur de retour|Description|  
|----------------------|-----------------|  
|\< 0|La sous\-chaîne de `string1` est inférieure à la sous\-chaîne de `string2`.|  
|0|La sous\-chaîne de `string1` est identique à la sous\-chaîne de `string2`.|  
|\> 0|La sous\-chaîne de `string1` est supérieure à la sous\-chaîne de `string2`.|  
  
 En cas d'erreur, `_mbsnbcmp` retourne `_NLSCMPERROR`, qui est défini dans String.h et Mbstring.h.  
  
## Notes  
 La fonction `_mbsnbicmp` effectue une comparaison ordinale des `count` \(au plus\) premiers octets de `string1` et de `string2`.  La comparaison est effectuée en convertissant chaque caractère en minuscule ; `_mbsnbcmp` est une version de `_mbsnbicmp` qui respecte la casse.  La comparaison se termine si un caractère null de fin est atteint dans l'une ou l'autre des chaînes avant que `count` caractères soient comparés.  Si les chaînes sont égales quand un caractère null de fin est atteint dans l'une ou l'autre des chaînes avant que `count` caractères soient comparés, la chaîne la plus courte est considérée comme étant inférieure.  
  
 `_mbsnbicmp`  est similaire à `_mbsnicmp`, sauf qu'elle compare des chaînes jusqu'à `count` octets au lieu de les comparer par caractères.  
  
 La comparaison de deux chaînes contenant des caractères qui se trouvent entre « Z » et « a » dans la table ASCII \(« \[ », « \\ », « \] », « ^ », « \_ » et « ' »\) donne des résultats différents selon leur casse.  Par exemple, les deux chaînes « `ABCDE` » et « `ABCD^` » se comparent d'une certaine façon si la comparaison est en minuscules \(« `abcde` » \> « `abcd^` »\) et d'une autre façon \(« `ABCDE` » \< « `ABCD^` »\) si elle est en majuscules.  
  
 `_mbsnbicmp` reconnaît les séquences de caractères multioctets en fonction de la [page de codes multioctets](../../c-runtime-library/code-pages.md) en cours d'utilisation.  Elle n'est pas affectée par les paramètres régionaux actuels.  
  
 Si `string1` ou `string2` est un pointeur null, `_mbsnbicmp` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, cette fonction retourne `_NLSCMPERROR` et définit à `errno` à `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsnbicmp`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple relatif à [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)