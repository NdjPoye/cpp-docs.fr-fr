---
title: "_mbccpy_s, _mbccpy_s_l | Microsoft Docs"
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
  - "_mbccpy_s"
  - "_mbccpy_s_l"
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
  - "_mbccpy_s_l"
  - "mbccpy_s_l"
  - "mbccpy_s"
  - "_mbccpy_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbccpy_s (fonction)"
  - "_mbccpy_s_l (fonction)"
  - "_tccpy_s (fonction)"
  - "_tccpy_s_l (fonction)"
  - "mbccpy_s (fonction)"
  - "mbccpy_s_l (fonction)"
  - "tccpy_s (fonction)"
  - "tccpy_s_l (fonction)"
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 30
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbccpy_s, _mbccpy_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie un caractère multi\-octets d'une chaîne à une autre chaîne.  Ces versions [\_mbccpy, \_mbccpy\_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `dest`  
 Destination de copie.  
  
 \[in\] `buffSizeInBytes`  
 Taille de la mémoire tampon de destination.  
  
 \[out\] `pCopied`  
 Rempli avec le nombre d'octets copiés \(1 ou 2 si réussi\).  Passez `NULL` si vous ne vous inquiétez pas du nombre.  
  
 \[in\] `src`  
 Caractère multi\-octets à copier.  
  
 \[in\] `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  Si `src` ou `dest` est `NULL`, ou si plus que `buffSizeinBytes` octets sont copiés vers `dest`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction retourne `EINVAL` et `errno` est défini à `EINVAL`.  
  
## Notes  
 La fonction `_mbccpy_s` copie un caractère multi\-octets depuis `src` vers `dest`.  Si `src` ne pointe pas vers l'octet de tête d'un caractère multi\-octets déterminé par un appel implicite à [\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), l'octet unique sur lequel pointe `src` est copié.  Si `src` pointe vers un octet de tête mais que l'octet suivant est 0 donc invalide, alors 0 est copié vers `dest`, `errno` a la valeur `EILSEQ`, et la fonction retourne `EILSEQ`.  
  
 `_mbccpy_s` n'ajoute pas de terminateur null ; Toutefois, si `src` pointe vers un caractère Null, ce null est copié vers `dest` \(c'est simplement une copie normale d'un seul octet\).  
  
 La valeur de `pCopied` est remplie avec le nombre d'octets copiés.  Les valeurs possibles sont 1 et 2 si l'opération réussit.  Si `NULL` est passé, ce paramètre est ignoré.  
  
|`src`|copié à `dest`|`pCopied`|Valeur de retour|  
|-----------|--------------------|---------------|----------------------|  
|pas un octet de tête|pas un octet de tête|1|0|  
|0|0|1|0|  
|octet de tête suivi de non\-0|octet de tête suivi de non\-0|2|0|  
|octet de tête suivi de 0|0|1|`EILSEQ`|  
  
 Notez que la deuxième ligne est simplement un cas particulier de la première  Notez également que la table suppose `buffSizeInBytes` \>\= `pCopied`.  
  
 `_mbccpy_s` utilise les paramètres régionaux courants pour tout comportement dépendant des paramètres régionaux.  `_mbccpy_s_l` est identique à `_mbccpy_s` sauf que `_mbccpy_s_l` utilise les paramètres régionaux qui lui sont passés pour tout comportement dépendant des paramètres régionaux.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tccpy_s`|Mappe à la macro ou à la fonction inline|`_mbccpy_s`|Mappe à la macro ou à la fonction inline|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbccpy_s`|\<mbstring.h\>|  
|`_mbccpy_s_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)