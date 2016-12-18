---
title: "_ltoa, _ltow | Microsoft Docs"
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
  - "_ltoa"
  - "_ltow"
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
  - "ltow"
  - "_ltot"
  - "_ltoa"
  - "_ltow"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ltoa (fonction)"
  - "_ltow (fonction)"
  - "convertir des entiers"
  - "convertir des nombres, en chaînes"
  - "conversion d'un entier long en chaîne"
  - "ltoa (fonction)"
  - "ltow (fonction)"
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ltoa, _ltow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un entier long en chaîne.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md).  
  
## Syntaxe  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### Paramètres  
 `value`  
 Nombre devant être converti.  
  
 `str`  
 Chaîne de résultat.  
  
 `radix`  
 Base de `value`.  
  
## Valeur de retour  
 Chacune de ces fonctions renvoie un pointeur vers `str`.  Aucun retour d'erreur.  
  
## Notes  
 La fonction `_ltoa` convertit les chiffres de`value` en chaîne de caractères se terminant par null et stocke le résultat \(jusqu'à 33 octets\) dans `str`.  L'argument `radix` spécifie la base de `value`, qui doit être comprise entre 2 et 36.  Si `radix` est égal à 10 et que `value` est négative, le premier caractère de la chaîne stockée est le signe moins \(\-\).  `_ltow` est une version à caractères larges de `_ltoa`; l'argument `_ltow` et la valeur de retour de  sont des chaînes à caractères larges.  Chacune de ces fonctions est Microsoft\- détail.  
  
> [!IMPORTANT]
>  Pour empêcher les dépassements de mémoire tampon, assurez\-vous que la mémoire tampon de `str` est suffisamment grande pour contenir les chiffres convertis plus le caractère Null de fin et un caractère de signe.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h\>|  
|`_ltow`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [\_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## Équivalent .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)