---
title: "_mbccpy, _mbccpy_l | Microsoft Docs"
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
  - "_mbccpy"
  - "_mbccpy_l"
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
  - "_mbccpy"
  - "tccpy"
  - "ftccpy"
  - "mbccpy"
  - "_tccpy"
  - "_ftccpy"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbccpy (fonction)"
  - "_mbccpy_l (fonction)"
  - "_tccpy (fonction)"
  - "_tccpy_l (fonction)"
  - "mbccpy (fonction)"
  - "mbccpy_l (fonction)"
  - "tccpy (fonction)"
  - "tccpy_l (fonction)"
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbccpy, _mbccpy_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie un caractère multioctets d'une chaîne à une autre chaîne.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_mbccpy\_s, \_mbccpy\_s\_l](../../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
void _mbccpy(  
   unsigned char *dest,  
   const unsigned char *src   
);  
void _mbccpy_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `dest`  
 Destination de copie.  
  
 `src`  
 Caractère multioctets à copier.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Notes  
 La fonction `_mbccpy` copie un caractère multioctets de `src` à `dest`.  
  
 Cette fonction valide ses paramètres.  Si `_mbccpy` obtient un pointeur null pour `dest`, ou `src`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md)..  S'il l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL`.  
  
 `_mbccpy` utilise les paramètres régionaux courants pour tout comportement dépendant des paramètres régionaux.  `_mbccpy_l` est identique à `_mbccpy` sauf que `_mbccpy_l` utilise les paramètres régionaux qui lui sont passés pour tout comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 **Security Note** Utilisez une chaîne terminée par le caractère NULL.  La chaîne terminée par le caractère NULL ne doit pas dépasser la taille de la mémoire tampon de destination.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tccpy`|Mappe à la macro ou à la fonction inline|`_mbccpy`|Mappe à la macro ou à la fonction inline|  
|`_tccpy_l`|N\/A|`_mbccpy_l`|N\/A|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbccpy`|\<mbctype.h\>|  
|`_mbccpy_l`|\<mbctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)