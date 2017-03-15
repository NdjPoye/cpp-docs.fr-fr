---
title: "strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__wcserror_s"
  - "_strerror_s"
  - "_wcserror_s"
  - "strerror_s"
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
  - "wcserror_s"
  - "__wcserror_s"
  - "_tcserror_s"
  - "_wcserror_s"
  - "tcserror_s"
  - "strerror_s"
  - "_strerror_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wcserror_s (fonction)"
  - "_strerror_s (fonction)"
  - "_tcserror_s (fonction)"
  - "_wcserror_s (fonction)"
  - "messages d'erreur, obtenir"
  - "messages d'erreur, imprimer"
  - "messages d'erreur d'impression"
  - "strerror_s (fonction)"
  - "tcserror_s (fonction)"
  - "wcserror_s (fonction)"
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strerror_s, _strerror_s, _wcserror_s, __wcserror_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recevez un message d'erreur système \(`strerror_s`, `_wcserror_s`\) ou imprimez un message d'erreur défini par l'utilisateur \(`_strerror_s`, `__wcserror_s`\).  Il s'agit de versions de [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Mémoire tampon pour contenir la chaîne d'erreur.  
  
 `numberOfElements`  
 Taille des mémoires tampons.  
  
 `errnum`  
 Numéro de l'erreur.  
  
 `strErrMsg`  
 messages fournis par l'utilisateur.  
  
## Valeur de retour  
 Zéro si l'opération a réussi, code d'erreur en cas de échec.  
  
### Conditions d'erreur  
  
|`buffer`|`numberOfElements`|`strErrMsg`|Contenu de `buffer`.|  
|--------------|------------------------|-----------------|--------------------------|  
|`NULL`|any|any|N\/A|  
|any|0|any|non modifié|  
  
## Notes  
 La fonction `strerror_s` mappe `errnum` à une chaîne de message d'erreur, en retournant la chaîne dans `buffer`.  `_strerror_s` ne prend pas le numéro d'erreur ; il utilise la valeur `errno` pour déterminer le message approprié.  Ni `strerror_s` ni `_strerror_s` n'impriment réellement le message: Pour cela, vous devez appeler une fonction de sortie comme [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md):  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 Si `strErrMsg` est `NULL`, `_strerror_s` retourne une chaîne dans `buffer` contenant le message d'erreur système pour le dernier appel de bibliothèque qui a produit une erreur.  La chaîne de message d'erreur est terminée par le caractère de saut de ligne \("\\ n "\).  Si `strErrMsg` n'est pas égal à `NULL`, `_strerror_s` retourne une chaîne dans `buffer` contenant \(dans l'ordre\) votre message de chaîne, deux\-points, un espace, le message d'erreur système pour le dernier appel de bibliothèque pour produire une erreur, et un caractère de saut de ligne.  Votre message de chaîne peut être, au plus, de 94 caractères.  
  
 Ces fonctions tronquent le message d'erreur si sa longueur dépasse `numberOfElements` \-1.  Chaîne résultante dans `buffer` se termine toujours par null.  
  
 Le vrai numéro d'erreur pour `_strerror_s` apparaît dans la variable [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Les messages d'erreur système sont accessibles via le variable [\_sys\_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), qui est un tableau du nombre par erreur classé par messages.  `_strerror_s` accède au message d'erreur adapté en utilisant la valeur `errno` comme index à la variable `_sys_errlist`.  La valeur de la variable [\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) est définie comme nombre maximal d'éléments du tableau `_sys_errlist`.  Pour produire des résultats exacts, appelez `_strerror_s` immédiatement après une routine de bibliothèque retourne avec une erreur.  Sinon, les appels suivants à `strerror_s` ou `_strerror_s` peuvent remplacer la valeur `errno`.  
  
 `_wcserror_s` et `__wcserror_s`, sont des versions à caractères larges de `strerror_s`, et `_strerror_s`, respectivement.  
  
 Ces fonctions valident leurs paramètres.  Si la mémoire tampon est `NULL` ou si le paramètre est de taille 0, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, les fonctions retournent \-1 `EINVAL` et attribuent à `errno` la valeur `EINVAL`.  
  
 `_strerror_s, _wcserror_s,` et `__wcserror_s` ne sont pas parties de la définition ANSI mais sont plutôt des extensions Microsoft de celui\-ci.  Ne les utilisez pas où la portabilité est souhaitée ; pour compatibilité ANSI, utilisez plutôt `strerror_s` .  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strerror_s`, `_strerror_s`|\<string.h\>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## Équivalent .NET Framework  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)