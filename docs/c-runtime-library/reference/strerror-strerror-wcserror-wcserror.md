---
title: "strerror, _strerror, _wcserror, __wcserror | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strerror"
  - "_strerror"
  - "_wcserror"
  - "__wcserror"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__sys_errlist"
  - "wcserror"
  - "_strerror"
  - "__wcserror"
  - "strerror"
  - "__sys_nerr"
  - "_tcserror"
  - "_wcserror"
  - "tcserror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__sys_errlist"
  - "__sys_nerr"
  - "__wcserror (fonction)"
  - "_strerror (fonction)"
  - "_tcserror (fonction)"
  - "_wcserror (fonction)"
  - "messages d'erreur, obtenir"
  - "messages d'erreur, imprimer"
  - "messages d'erreur d'impression"
  - "strerror (fonction)"
  - "tcserror (fonction)"
  - "wcserror (fonction)"
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strerror, _strerror, _wcserror, __wcserror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient une chaîne de message d'erreur système \(`strerror`, `_wcserror`\) ou met en forme une chaîne de message d'erreur fournie par l'utilisateur \(`_strerror`, `__wcserror`\).  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md).  
  
## Syntaxe  
  
```  
char *strerror(    int errnum  ); char *_strerror(    const char *strErrMsg  ); wchar_t * _wcserror(    int errnum  ); wchar_t * __wcserror(    const wchar_t *strErrMsg  );  
```  
  
#### Paramètres  
 `errnum`  
 Numéro d'erreur.  
  
 `strErrMsg`  
 Message fourni par l'utilisateur.  
  
## Valeur de retour  
 Toutes ces fonctions retournent un pointeur vers la chaîne de message d'erreur.  Les appels suivants peuvent remplacer la chaîne.  
  
## Notes  
 La fonction `strerror` mappe `errnum` à une chaîne de message d'erreur et retourne un pointeur vers la chaîne.  Ni `strerror` ni `_strerror` n'impriment réellement le message : pour cela, vous devez appeler une fonction de sortie telle que [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) :  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 Si `strErrMsg` est passé comme valeur `NULL`, `_strerror` retourne un pointeur vers une chaîne qui contient le message d'erreur système pour le dernière appel de bibliothèque qui a généré l'erreur.  La chaîne de message d'erreur se termine par le caractère de saut de ligne \('\\n'\).  Si `strErrMsg` n'est pas égal à `NULL`, `_strerror` retourne un pointeur vers une chaîne qui contient \(dans l'ordre\) votre message de type chaîne, deux\-points, un espace, le message d'erreur système pour le dernier appel de bibliothèque qui a généré une erreur et un caractère de saut de ligne.  La longueur maximale de votre message de type chaîne est de 94 caractères.  
  
 Le numéro d'erreur effectif de `_strerror` est stocké dans la variable [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Pour générer des résultats précis, appelez `_strerror` de suite après le retour avec erreur d'une routine de bibliothèque.  Sinon, les appels suivants à `strerror` ou `_strerror` peuvent remplacer la valeur `errno`.  
  
 `_wcserror` et `__wcserror` sont, respectivement, des versions à caractères larges de `strerror` et `_strerror`.  
  
 `_strerror`, `_wcserror` et `__wcserror` ne font pas partie de la définition ANSI ; ce sont des extensions Microsoft et nous vous déconseillons de les utiliser là où vous voulez un code portable.  Pour une compatibilité ANSI, utilisez plutôt `strerror`.  
  
 Pour obtenir des chaînes d'erreur, nous vous recommandons `strerror` ou `_wcserror` plutôt que les macros déconseillées [\_sys\_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) et [\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) et les fonctions internes déconseillées `__sys_errlist` et `__sys_nerr`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strerror`|\<string.h\>|  
|`_strerror`|\<string.h\>|  
|`_wcserror`, `__wcserror`|\<string.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Voir l'exemple pour [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## Équivalent .NET Framework  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)