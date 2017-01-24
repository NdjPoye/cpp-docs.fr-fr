---
title: "_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l | Microsoft Docs"
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
  - "_vscprintf"
  - "_vscprintf_l"
  - "_vscwprintf_l"
  - "_vscwprintf"
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
apitype: "DLLExport"
f1_keywords: 
  - "vscprintf_l"
  - "vscwpeintf"
  - "_vscwprintf"
  - "_vsctprintf"
  - "_vscprintf"
  - "vscwprintf_l"
  - "vscprintf"
  - "_vscwprintf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vscprintf (fonction)"
  - "_vscprintf_l (fonction)"
  - "_vsctprintf (fonction)"
  - "_vsctprintf_l (fonction)"
  - "_vscwprintf (fonction)"
  - "_vscwprintf_l (fonction)"
  - "texte mis en forme (C++)"
  - "vscprintf (fonction)"
  - "vscprintf_l (fonction)"
  - "vsctprintf (fonction)"
  - "vsctprintf_l (fonction)"
  - "vscwprintf (fonction)"
  - "vscwprintf_l (fonction)"
ms.assetid: 1bc67d3d-21d5-49c9-ac8d-69e26b16a3c3
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne le nombre de caractères dans la chaîne mise en forme à un pointeur vers une liste d'arguments.  
  
## Syntaxe  
  
```  
int _vscprintf(  
   const char *format,  
   va_list argptr   
);  
int _vscprintf_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vscwprintf(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vscwprintf_l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### Paramètres  
 `format`  
 Chaîne de contrôle de format.  
  
 `argptr`  
 Pointeur vers la liste d'arguments.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 `_vscprintf` retourne le nombre de caractères qui sont générés si la chaîne désignée par la liste d'arguments est imprimée ou envoyée à un fichier ou dans une mémoire tampon à l'aide de codes de mise en forme spécifiés.  La valeur retournée n'inclut pas le caractère NULL terminant la chaine.  `_vscwprintf` effectue la même fonction pour des caractères larges.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 Si `format` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoient \-1 et définie `errno` avec la valeur `EINVAL`.  
  
## Notes  
 Chaque `argument` \(si il y en a\) est converti selon la spécification du format correspondant `format`.  Le format se compose de caractères ordinaires et a la même forme et fonction que l'argument `format` pour [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
> [!IMPORTANT]
>  Vérifiez que si `format` est une chaîne définie par l'utilisateur, elle a la valeur NULL à la fin et a le nombre et le type des paramètres corrects.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_vsctprintf`|`_vscprintf`|`_vscprintf`|`_vscwprintf`|  
|`_vsctprintf_l`|`_vscprintf_l`|`_vscprintf_l`|`_vscwprintf_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_vscprintf`, `_vscprintf_l`|\<stdio.h\>|  
|`_vscwprintf`, `_vscwprintf_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Voyez l'exemple pour [vsprintf](../../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)