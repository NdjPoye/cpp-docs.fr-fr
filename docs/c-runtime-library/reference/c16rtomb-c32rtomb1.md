---
title: "c16rtomb, c32rtomb1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "c16rtomb"
  - "c32rtomb"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c16rtomb"
  - "c32rtomb"
  - "uchar/c16rtomb"
  - "uchar/c32rtomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "c16rtomb (fonction)"
  - "c32rtomb (fonction)"
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# c16rtomb, c32rtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir un caractère large UTF\-16 ou UTF\-32 en caractère multioctet dans les paramètres régionaux actuels.  
  
## Syntaxe  
  
```  
size_t c16rtomb(  
    char *mbchar,   
    char16_t wchar,  
    mbstate_t *state  
);  
size_t c32rtomb(  
    char *mbchar,   
    char32_t wchar,  
    mbstate_t *state  
);  
```  
  
#### Paramètres  
 \[out\] `mbchar`  
 Pointeur vers un tableau pour stocker le caractère multioctet converti.  
  
 \[in\] `wchar`  
 Caractère large à convertir.  
  
 \[in, out\] `state`  
 Pointeur vers un objet `mbstate_t`.  
  
## Valeur de retour  
 Nombre d’octets stockés dans un objet tableau `mbchar`, y compris les séquences de décalage. Si `wchar` n'est pas un caractère large valide, la valeur \(`size_t`\)\(\-1\) est retournée, `errno` prend la valeur `EILSEQ`, et la valeur de `state` est non spécifiée.  
  
## Notes  
 La fonction `c16rtomb` convertit le caractère UTF\-16 `wchar` en séquence de caractères étroits multioctets équivalente dans les paramètres régionaux actuels. Si `mbchar` n’est pas un pointeur null, la fonction stocke la séquence convertie dans l’objet tableau vers lequel `mbchar` pointe. Jusqu’à `MB_CUR_MAX` octets sont stockés dans `mbchar`, et `state` prend comme valeur l’état du décalage multioctet qui en résulte.    Si `wchar` est un caractère large null, une séquence nécessaire pour restaurer l’état du décalage initial est stockée, si nécessaire, suivie du caractère null, et `state` prend comme valeur l’état de conversion initial. La fonction `c32rtomb` est identique, mais elle convertit un caractère UTF\-32.  
  
 Si `mbchar` est un pointeur null, le comportement équivaut à un appel à la fonction qui remplace `mbchar` par une mémoire tampon interne et `wchar` par un caractère null large.  
  
 L’objet d’état de conversion `state` vous permet d’effectuer des appels ultérieurs à cette fonction et à d’autres fonctions redémarrables qui tiennent à jour l’état du décalage des caractères multioctets de sortie. Les résultats ne sont pas définis lorsque vous combinez l’utilisation de fonctions redémarrables et non redémarrables, ou si un appel à `setlocale` est effectué entre des appels de fonctions redémarrables.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`c16rtomb`, `c32rtomb`|C, C\+\+: \<uchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtoc16, mbrtoc32](../../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)