---
title: "_mbsbtype, _mbsbtype_l | Microsoft Docs"
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
  - "_mbsbtype_l"
  - "_mbsbtype"
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
  - "mbsbtype"
  - "mbsbtype_l"
  - "_mbsbtype_l"
  - "_mbsbtype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsbtype (fonction)"
  - "_mbsbtype_l (fonction)"
  - "mbsbtype (fonction)"
  - "mbsbtype_l (fonction)"
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsbtype, _mbsbtype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne le type d'octets dans une chaîne.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### Paramètres  
 `mbstr`  
 Adresse une séquence de caractères multioctets.  
  
 `count`  
 Décalage d'octet à partir de la tête de chaîne.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_mbsbtype` et `_mbsbtype_l`retournent une valeur entière indiquant le résultat du test dans l'octet spécifié.  Les constantes manifestes dans le tableau suivant sont définies dans Mbctype.h.  
  
|Valeur de retour|Type d'octet|  
|----------------------|------------------|  
|`_MBC_SINGLE` \(0\)|Caractère simple octet.  Par exemple, dans la page de codes 932, `_mbsbtype` retourne 0 si l'octet spécifié se trouve dans la plage 0x20 – 0x7E ou 0xA1 – 0xDF.|  
|`_MBC_LEAD` \(1\)|Octet de tête de caractère multioctet.  Par exemple, dans la page de codes 932, `_mbsbtype` retourne 1 si l'octet spécifié se trouve dans la plage 0x81 – 0x9F ou 0xE0 – 0xFC.|  
|`_MBC_TRAIL` \(2\)|Octet de fin multioctets.  Par exemple, dans la page de codes 932, `_mbsbtype` retourne 2 si l'octet spécifié se trouve dans la plage 0x40 – 0x7E ou 0x80 – 0xFC.|  
|`_MBC_ILLEGAL` \(–1\)|La chaîne `NULL`, le caractère non valide, ou l'octet `NULL` a été trouvé avant l'octet d'offset `count` dans `mbstr`.|  
  
## Notes  
 La fonction `_mbsbtype` détermine le type d'un octet dans une chaîne de caractères multioctets.  La fonction examine uniquement l'octet à l'offset `count` dans `mbstr`, en ignorant les caractères non valides avant l'octet spécifié.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  La version de cette fonction sans le suffixe `_l` utilise les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; la version avec le suffixe `_l` est identique, sauf qu'elle utilise à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si la chaîne donnée est `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini comme `EINVAL` et la fonction retourne `_MBC_ILLEGAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_mbsbtype`|\<mbstring.h\>|\<mbctype.h\>\*|  
|`_mbsbtype_l`|\<mbstring.h\>|\<mbctype.h\>\*|  
  
 \* Pour les constantes manifestes utilisées comme valeurs de retour.  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## Voir aussi  
 [Classification d'octets](../../c-runtime-library/byte-classification.md)