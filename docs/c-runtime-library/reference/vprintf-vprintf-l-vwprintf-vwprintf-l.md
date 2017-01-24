---
title: "vprintf, _vprintf_l, vwprintf, _vwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vprintf"
  - "_vwprintf_l"
  - "_vprintf_l"
  - "vwprintf"
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
  - "vwprintf"
  - "_vtprintf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vprintf_l (fonction)"
  - "_vtprintf (fonction)"
  - "_vtprintf_l (fonction)"
  - "_vwprintf_l (fonction)"
  - "texte mis en forme (C++)"
  - "vprintf (fonction)"
  - "vprintf_l (fonction)"
  - "vtprintf (fonction)"
  - "vtprintf_l (fonction)"
  - "vwprintf (fonction)"
  - "vwprintf_l (fonction)"
ms.assetid: 44549505-00a0-4fa7-9a85-f2e666f55a38
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vprintf, _vprintf_l, vwprintf, _vwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ecrit une sortie formatée en utilisant un pointeur vers une liste d'arguments.  Des versions plus sécurisées de ces fonctions sont disponibles; consultez [vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md).  
  
## Syntaxe  
  
```  
int vprintf(  
   const char *format,  
   va_list argptr   
);  
int _vprintf_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vwprintf(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vwprintf_l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### Paramètres  
 `format`  
 Spécification de format.  
  
 `argptr`  
 Pointeur vers la liste d'arguments.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 `vprintf` et `vwprintf` renvoient le nombre de caractères écrits, sans le caractère null de fin, ou une valeur négative si une erreur de sortie se produit.  Si `format` est un pointeur null, ou si la chaîne de format contient des caractères de mise en forme valides, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie \-1 et definit `errno` avec la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes d'erreur et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chacune de ces fonctions prend un pointeur vers une liste d'arguments, puis formate et écrit les données données dans `stdout`.  
  
 `vwprintf` est la version à caractères élargis de `vprintf`; les deux fonctions se comportent de la même manière si le flux est ouvert en mode ANSI.  `vprintf` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  Notez que les chaînes de format non valides sont détectées et provoquent une erreur.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_vtprintf`|`vprintf`|`vprintf`|`vwprintf`|  
|`_vtprintf_l`|`_vprintf_l`|`_vprintf_l`|`_vwprintf_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`vprintf`, `_vprintf_l`|\<stdio.h\> et \<stdarg.h\>|\<varargs.h\>\*|  
|`vwprintf`, `_vwprintf_l`|\<stdio.h\> ou \<wchar.h\>, et \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Requis pour la compatibilité UNIX V.  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)