---
title: "strcat, wcscat, _mbscat | Microsoft Docs"
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
  - "_mbscat"
  - "wcscat"
  - "strcat"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbscat"
  - "_ftcscat"
  - "_tcscat"
  - "strcat"
  - "wcscat"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcscat (fonction)"
  - "_mbscat (fonction)"
  - "_tcscat (fonction)"
  - "ajouter des chaînes"
  - "concaténer des chaînes"
  - "ftcscat (fonction)"
  - "mbscat (fonction)"
  - "strcat (fonction)"
  - "chaînes (C++), ajouter"
  - "chaînes (C++), concaténer"
  - "tcscat (fonction)"
  - "wcscat (fonction)"
ms.assetid: c89c4ef1-817a-44ff-a229-fe22d06ba78a
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcat, wcscat, _mbscat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Attache une chaîne.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [strcat\_s, wcscat\_s, \_mbscat\_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md).  
  
> [!IMPORTANT]
>  `_mbscat_s` ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *strcat(  
   char *strDestination,  
   const char *strSource   
);  
wchar_t *wcscat(  
   wchar_t *strDestination,  
   const wchar_t *strSource   
);  
unsigned char *_mbscat(  
   unsigned char *strDestination,  
   const unsigned char *strSource   
);  
template <size_t size>  
char *strcat(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
wchar_t *wcscat(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
unsigned char *_mbscat(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### Paramètres  
 `strDestination`  
 Chaîne cible finissant par Null.  
  
 `strSource`  
 Chaîne source se terminant par null.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne la chaîne de destination \(`strDestination`\).  Aucune valeur de retour n'est réservée pour indiquer une erreur.  
  
## Notes  
 La fonction `strcat` ajoute `strSource` à `strDestination` et arrête la chaîne résultante avec un caractère Null.  Le caractère initial de `strSource` remplace le caractère null de fin de `strDestination`.  Le comportement de `strcat` est non défini si les chaînes source et de destination se superposent.  
  
> [!IMPORTANT]
>  Comme `strcat` ne vérifie pas l'espace suffisant dans `strDestination` avant de copier `strSource`, c'est une cause potentielle de dépassements de mémoire tampon.  Si possible, utilisez [strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md) à la place.  
  
 `wcscat` et `_mbscat` sont des versions à caractères élargis et à caractères multi\-octets de `strcat`.  Les arguments et la valeur de retour de `wcscat` sont des chaînes à caractères larges ; ceux de `_mbscat` sont des chaînes de caractères multioctets.  Ces trois fonctions se comportent sinon de façon identique.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcscat`|`strcat`|`_mbscat`|`wcscat`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strcat`|\<string.h\>|  
|`wcscat`|\<string.h\> ou \<wchar.h\>|  
|`_mbscat`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md).  
  
## Équivalent .NET Framework  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)