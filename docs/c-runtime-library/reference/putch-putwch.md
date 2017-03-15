---
title: "_putch, _putwch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putwch"
  - "_putch"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_putch"
  - "putwch"
  - "_putwch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putch (fonction)"
  - "_putwch (fonction)"
  - "caractères, écrire"
  - "console, écrire des caractères dans"
  - "putch (fonction)"
  - "putwch (fonction)"
ms.assetid: 3babc7cf-e333-405d-8449-c788d61d51aa
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _putch, _putwch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit un caractère dans la console.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
  
      int _putch(  
int c   
);  
wint_t _putwch(  
   wchar_t c  
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à envoyer en sortie.  
  
## Valeur de retour  
 En cas de réussite, retourne `c`.  Si `_putch` échoue, elle retourne `EOF`; si **\_putwch** échoue, elle retourne **WEOF**.  
  
## Notes  
 Ces fonctions écrivent le caractère `c` directement dans la console, sans le mettre en mémoire tampon.  Dans Windows NT, **\_putwch**écrit les caractères Unicode à l'aide des paramètres régionaux de console.  
  
 Les versions avec le suffixe **\_nolock** sont identiques mais elles ne sont pas protégées contre les interférences en provenance d'autres threads.  Pour plus d'informations, consultez `_putch_nolock`, `_putwch_nolock`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|**\_puttch**|`_putch`|`_putch`|**\_putwch**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_putch`|\<conio.h\>|  
|**\_putwch**|\<conio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Consultez l'exemple de [\_getch](../../c-runtime-library/reference/getch-getwch.md).  
  
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)