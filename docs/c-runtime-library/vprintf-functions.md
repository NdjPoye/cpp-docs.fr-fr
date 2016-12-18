---
title: "Fonctions vprintf | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "vprintf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "texte mis en forme (C++)"
  - "vprintf (fonction)"
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctions vprintf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chacune des fonctions `vprintf` prend un pointeur vers une liste d'arguments, puis met en forme et écrit les données fournies vers une destination particulière.  Les fonctions diffèrent dans la validation des paramètres exécutée, que les fonctions acceptent les chaînes de caractères larges ou écrites sur un octet, la destination de sortie, et la prise en charge de la spécification de l'ordre dans lequel les paramètres sont utilisés dans la chaîne de format.  
  
|||  
|-|-|  
|[\_vcprintf, \_vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf\_s, \_vfprintf\_s\_l, vfwprintf\_s, \_vfwprintf\_s\_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|  
|[vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|  
|[\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|[vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|  
|[\_vscprintf, \_vscprintf\_l, \_vscwprintf, \_vscwprintf\_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[\_vsnprintf, \_vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|  
  
## Notes  
 Les fonctions `vprintf` sont semblables à leurs fonctions d'homologues comme indiqué dans le tableau suivant.  Toutefois, chaque fonction `vprintf` reçoit un pointeur vers une liste d'arguments, alors que chacune des fonctions homologues acceptent une liste d'arguments.  
  
 Ces fonctions formatent les données pour la sortie vers les destination comme ce qui suit.  
  
|Fonction|Fonction homologues|Destination de sortie|Validation de paramètre|Prise en charge du paramètre positionnel|  
|--------------|-------------------------|---------------------------|-----------------------------|----------------------------------------------|  
|`_vcprintf`|[\_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Contrôle du caractère null.|non|  
|`_vcwprintf`|[\_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Contrôle du caractère null.|non|  
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|Contrôle du caractère null.|non|  
|**vfprintf\_p**|[fprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|Contrôle du format null et valide.|oui|  
|`vfprintf_s`|[fprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|Contrôle du format null et valide.|non|  
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|Contrôle du caractère null.|non|  
|**vfwprintf\_p**|[fwprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|Contrôle du format null et valide.|oui|  
|`vfwprintf_s`|[fwprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|Contrôle du format null et valide.|non|  
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Contrôle du caractère null.|non|  
|**vprintf\_p**|[printf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Contrôle du format null et valide.|oui|  
|`vprintf_s`|[printf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Contrôle du format null et valide.|non|  
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Contrôle du caractère null.|non|  
|**vwprintf\_p**|[wprintf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Contrôle du format null et valide.|oui|  
|`vwprintf_s`|[wprintf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Contrôle du format null et valide.|non|  
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du caractère null.|non|  
|**vsprintf\_p**|[sprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du format null et valide.|oui|  
|`vsprintf_s`|[sprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du format null et valide.|non|  
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du caractère null.|non|  
|**vswprintf\_p**|[swprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du format null et valide.|oui|  
|`vswprintf_s`|[swprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du format null et valide.|non|  
|`_vscprintf`|[\_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du caractère null.|non|  
|`_vscwprintf`|[\_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du caractère null.|non|  
|`_vsnprintf`|[\_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du caractère null.|non|  
|`_vsnwprintf`|[\_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|mémoire désignée par *mémoire tampon*|Contrôle du caractère null.|non|  
  
 L'argument `argptr` est de type `va_list`, défini dans VARARGS.H et STDARG.H.  La variable `argptr` doit être initialisée par **va\_start,** et peut être réinitialisée par les appels suivants `va_arg` ; `argptr` pointe ensuite au début d'une liste d'arguments qui sont convertis et transmis à la sortie en fonction des caractéristiques correspondantes dans l'argument *format*.  *format* a la même forme et fonction que l'argument *format* pour [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  Aucune de ces fonctions n'appelle `va_end`.  Pour une description plus complète de chaque fonction `vprintf`, consultez la description de sa fonction homologue comme indiqué dans le tableau précédent.  
  
 `_vsnprintf` diffère de **vsprintf** car il n'écrit pas plus que *nombre* octets dans *mémoire tampon*.  
  
 Les versions de ces fonctions avec l'infixe **w** dans le nom sont des versions de caractères larges des fonctions correspondantes sans l'infixe **w** ; dans chacune de ces fonctions de caractères étendus, *mémoire tampon* et *format* sont des chaînes de caractères larges.  Sinon, chaque fonction de caractères étendus se comporte de manière identique à sa fonction homologues dans SBCS.  
  
 Les versions de ces fonctions avec les suffixes **\_s** et **\_p** sont les versions les plus sécurisées.  Ces versions valident les chaînes de format et génèrent une exception si la chaîne de format n'est pas correctement formée \(par exemple, si des caractères de mise en forme non valides sont utilisés\).  
  
 Les versions de ces fonctions avec le suffixe **\_p** permettent de spécifier l'ordre dans lequel les arguments fournis sont substitués dans la chaîne de format.  Pour plus d'informations, consultez [Paramètres positionnels printf\_p](../c-runtime-library/printf-p-positional-parameters.md).  
  
 Pour **vsprintf**, `vswprintf`, `_vsnprintf` et `_vsnwprintf`, si une copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
> [!IMPORTANT]
>  Assurez\-vous que *format* n'est pas une chaîne définie par l'utilisateur.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  Si vous utilisez les versions sécurisées de ces fonctions \(les suffixes **\_s** ou **\_p** \), une chaîne de format fournie par l'utilisateur peut lever une exception de paramètre non valide si la chaîne fournie par l'utilisateur contient des caractères de mise en forme non valides.  
  
## Voir aussi  
 [E\/S de flux](../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)