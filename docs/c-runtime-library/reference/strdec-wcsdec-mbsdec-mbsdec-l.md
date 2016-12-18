---
title: "_strdec, _wcsdec, _mbsdec, _mbsdec_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsdec"
  - "_strdec"
  - "_mbsdec"
  - "_mbsdec_l"
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
  - "_strdec"
  - "mbsdec_l"
  - "strdec"
  - "_mbsdec"
  - "_mbsdec_l"
  - "mbsdec"
  - "wcsdec"
  - "_wcsdec"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsdec (fonction)"
  - "_mbsdec_l (fonction)"
  - "_strdec (fonction)"
  - "_tcsdec (fonction)"
  - "_wcsdec (fonction)"
  - "mbsdec (fonction)"
  - "mbsdec_l (fonction)"
  - "strdec (fonction)"
  - "tcsdec (fonction)"
  - "wcsdec (fonction)"
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdec, _wcsdec, _mbsdec, _mbsdec_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déplace un pointeur de chaîne d'un caractère en arrière.  
  
> [!IMPORTANT]
>  `mbsdec` and `mbsdec_l` ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
unsigned char *_strdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned wchar_t *_wcsdec(  
   const unsigned wchar_t *start,  
   const unsigned wchar_t *current   
);  
unsigned char *_mbsdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned char *_mbsdec_l(  
   const unsigned char *start,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `start`  
 Pointeur à tout caractère \(ou pour `_mbsdec` et \_`mbsdec_l`, le premier octet de tout caractère multi\-octets\) dans la chaîne source ; `start` doit précéder `current` dans la chaîne source.  
  
 `current`  
 Pointeur à tout caractère \(ou pour `_mbsdec` et \_`mbsdec_l`, le premier octet de tout caractère multi\-octets\) dans la chaîne source ; `current` doit suivre `start` dans la chaîne source.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_mbsdec`, \_`mbsdec_l`, `_strdec`, et `_wcsdec` retournent chacune un pointeur vers le caractère qui précède immédiatement `current`; `_mbsdec` retourne `NULL` si la valeur `start` est supérieure ou égale à celle d'un `current`.  les cartes d'un`_tcsdec` à un de ces fonctions et sa valeur de retour dépend du mappage.  
  
## Notes  
 Les fonctions `_mbsdec` et `_mbsdec_l` renvoient un pointeur vers le premier octet du caractère multi\-octets qui précède immédiatement `current` dans la chaîne qui contient `start`.  
  
 La valeur de sortie est affectée par le paramètre du paramètre de catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) .  `_mbsdec` identifie des séquences de caractères multi\-octets d'après les paramètres régionaux qui sont actuellement utilisées, tandis que `_mbsdec_l` est identique mais il utilise à la place des paramètres régionaux qui sont passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `start` ou `current` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie `EINVAL` et définit `errno` avec la valeur `EINVAL`.  
  
> [!IMPORTANT]
>  Ces fonctions peuvent être vulnérables aux menaces de dépassement de mémoire tampon.  Les dépassements de mémoire tampon peuvent être utilisés pour les attaques du système, car ils peuvent provoquer une élévation des privilèges injustifiée.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsdec`|`_strdec`|`_mbsdec`|`_wcsdec`|  
  
 `_strdec` et `_wcsdec` sont des versions à caractères élargis et à caractères simple\-octets de `_mbsdec` et `_mbsdec_l`.  `_strdec` et `_wcsdec` sont fournis uniquement pour ce mappage et ne doivent pas être utilisés sinon.  
  
 Pour plus d’informations, consultez [Utilisation des mappages de texte générique](../../c-runtime-library/using-generic-text-mappings.md) et [Mappages de texte générique](../../c-runtime-library/generic-text-mappings.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_mbsdec`|\<mbstring.h\>|\<mbctype.h\>|  
|`_mbsdec_l`|\<mbstring.h\>|\<mbctype.h\>|  
|`_strdec`|\<tchar.h\>||  
|`_wcsdec`|\<tchar.h\>||  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 L'exemple suivant illustre une utilisation de `_tcsdec`.  
  
```  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main()  
{  
   const TCHAR *str = _T("12345");  
   cout << "str: " << str << endl;  
  
   const TCHAR *str2;  
   str2 = str + 2;  
   cout << "str2: " << str2 << endl;  
  
   TCHAR *answer;  
   answer = _tcsdec( str, str2 );  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
 L'exemple suivant illustre une utilisation de `_mbsdec`.  
  
```  
#include <iostream>  
#include <mbstring.h>  
using namespace std;  
  
int main()   
{   
   char *str = "12345";  
   cout << "str: " << str << endl;  
  
   char *str2;  
   str2 = str + 2;   
   cout << "str2: " << str2 << endl;  
  
   unsigned char *answer;  
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));  
  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strinc, \_wcsinc, \_mbsinc, \_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strnextc, \_wcsnextc, \_mbsnextc, \_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)