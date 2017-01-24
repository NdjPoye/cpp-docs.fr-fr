---
title: "_ungetc_nolock, _ungetwc_nolock | Microsoft Docs"
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
  - "_ungetwc_nolock"
  - "_ungetc_nolock"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ungettc_nolock"
  - "ungetwc_nolock"
  - "ungetc_nolock"
  - "_ungetc_nolock"
  - "_ungetwc_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ungetc_nolock (fonction)"
  - "_ungettc_nolock (fonction)"
  - "_ungetwc_nolock (fonction)"
  - "caractères, push vers le flux"
  - "ungetc_nolock (fonction)"
  - "ungettc_nolock (fonction)"
  - "ungetwc_nolock (fonction)"
ms.assetid: aa02d5c2-1be1-46d2-a8c4-b61269e9d465
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ungetc_nolock, _ungetwc_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Repousse un caractère vers le flux.  
  
## Syntaxe  
  
```  
int _ungetc_nolock(  
   int c,  
   FILE *stream   
);  
wint_t _ungetwc_nolock(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à renvoyer.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 En cas de réussite, chacune de ces fonctions retourne l'argument `c`de caractère*.* Si `c` ne peut pas être refoulé ou si aucun caractère n'a été lu, le flux d'entrée est inchangé et `_ungetc_nolock` retourne `EOF`; `_ungetwc_nolock` retourne `WEOF`.  Si `stream` est `NULL`, `EOF` ou `WEOF` est retourné et `errno` a la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes d'erreur et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Ces fonctions sont les versions sans verrouillage de `ungetc` et de `ungetwc`.  Les versions avec le suffixe `_nolock` sont identiques mais elles ne sont pas protégées contre les interférence en provenance d'autres threads.  Elles peuvent être plus rapides car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ungettc_nolock`|`_ungetc_nolock`|`_ungetc_nolock`|`_ungetwc_nolock`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ungetc_nolock`|\<stdio.h\>|  
|`_ungetwc_nolock`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)