---
title: "_ultoa, _ultow | Microsoft Docs"
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
  - "_ultoa"
  - "_ultow"
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
  - "ultot"
  - "ultow"
  - "_ultoa"
  - "_ultow"
  - "_ultot"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ultoa (fonction)"
  - "_ultot (fonction)"
  - "_ultow (fonction)"
  - "convertir des entiers"
  - "convertir des nombres, en chaînes"
  - "entiers, convertir"
  - "ultot (fonction)"
  - "ultow (fonction)"
ms.assetid: 7a472dc4-5652-4513-93c3-3358522c23be
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ultoa, _ultow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un entier long non signé en une chaîne.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_ultoa\_s, \_ultow\_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md).  
  
## Syntaxe  
  
```  
char *_ultoa(  
   unsigned long value,  
   char *str,  
   int radix   
);  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ultoa(  
   unsigned long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ultow(  
   unsigned long value,  
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
 Base de `value`*.*  
  
## Valeur de retour  
 Chacune de ces fonctions renvoie un pointeur vers `str`.  Aucun retour d'erreur.  
  
## Notes  
 La fonction `_ultoa` convertit `value` en chaîne de caractères se terminant par null et stocke le résultat \(jusqu'à 33 octets\) dans `str`.  Aucune vérification des dépassements n'est effectuée.  `radix` spécifie la base de `value`; `radix` doit être comprise entre 2 et 36.  `_ultow` est une version à caractère élargi de `_ultoa`.  
  
> [!IMPORTANT]
>  Pour empêcher les dépassements de mémoire tampon, assurez\-vous que la mémoire tampon de `str` est suffisamment grande pour contenir les chiffres convertis plus le caractère Null de fin.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ultot`|`_ultoa`|`_ultoa`|`_ultow`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ultoa`|\<stdlib.h\>|  
|`_ultow`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [\_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## Équivalent .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)