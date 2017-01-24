---
title: "vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l | Microsoft Docs"
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
  - "_vsnprintf"
  - "_vsnprintf_l"
  - "_vsnwprintf"
  - "_vsnwprintf_l"
  - "_vsnprintf"
  - "_vsnprintf;"
  - "vsnprintf; _vsnprintf"
  - "_vsnwprintf;"
  - "_vsnprintf_l;"
  - "_vsnwprintf_l;"
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
  - "_vsnprintf"
  - "_vsnwprintf"
  - "_vsntprintf"
  - "vsnprintf"
  - "stdio/vsnprintf"
  - "stdio/_vsnprintf"
  - "stdio/_vsnprintf_l"
  - "stdio/_vsnwprintf"
  - "stdio/_vsnwprintf_l"
  - "_vsnprintf_l"
  - "_vsnwprintf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "vsntprintf (fonction)"
  - "_vsnwprintf_l (fonction)"
  - "vsnwprintf_l (fonction)"
  - "vsntprintf_l (fonction)"
  - "_vsntprintf (fonction)"
  - "_vsnprintf_l (fonction)"
  - "vsnprintf (fonction)"
  - "_vsntprintf_l (fonction)"
  - "vsnprintf_l (fonction)"
  - "_vsnwprintf (fonction)"
  - "_vsnprintf (fonction)"
  - "texte mis en forme (C++)"
  - "vsnwprintf (fonction)"
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
caps.latest.revision: 35
caps.handback.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrivez la sortie mise en forme en utilisant un pointeur désignant une liste d’arguments. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).  
  
## Syntaxe  
  
```  
int vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour la sortie.  
  
 `count`  
 Nombre maximal de caractères à écrire.  
  
 `format`  
 Spécification de format.  
  
 `argptr`  
 Pointeur vers la liste d'arguments.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 Le `vsnprintf` fonction retourne le nombre de caractères écrits, sans compter le caractère null de fin. Si la taille de mémoire tampon spécifiée par `count` n’est pas suffisamment grande pour contenir la sortie spécifiée par `format` et `argptr`, la valeur de retour de `vsnprintf` est le nombre de caractères qui doit être écrite, sans compter le caractère null, si `count` étaient suffisamment importantes. Si la valeur de retour est supérieure à `count` \- 1, le résultat a été tronqué. La valeur de retour \-1 indique qu’une erreur de codage s’est produite.  
  
 Les deux `_vsnprintf` et `_vsnwprintf` fonctions retournent le nombre de caractères écrits si le nombre de caractères à écrire est inférieure ou égale à `count`; Si le nombre de caractères à écrire est supérieur à `count`, ces fonctions renvoient \-1 indiquant que la sortie a été tronquée.  
  
 La valeur retournée par toutes ces fonctions n’inclut pas le caractère null de fin, un est écrit ou non. Lorsque `count` est égal à zéro, la valeur retournée est le nombre de caractères que les fonctions écririez pas, y compris tout caractère null de fin. Vous pouvez utiliser ce résultat à allouer suffisamment d’espace tampon pour la chaîne et le caractère null de fin et appelle ensuite la fonction pour remplir la mémoire tampon.  
  
 Si `format` est `NULL`, ou si `buffer` a la valeur NULL et `count` n’est pas égal à zéro, ces fonctions appellent le Gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et définissent `errno` avec la valeur `EINVAL`.  
  
## Notes  
 Chacune de ces fonctions prend un pointeur vers une liste d’arguments, met en forme les données et écrit jusqu’à `count` caractères dans la mémoire vers laquelle `buffer` pointe. La fonction `vsnprintf` écrit toujours une marque de fin null, même si elle tronque le résultat. Quand vous utilisez `_vsnprintf` et `_vsnwprintf`, la mémoire tampon est terminée par un caractère null uniquement s’il reste de la place à la fin \(autrement dit, si le nombre de caractères à écrire est inférieur à `count`\).  
  
> [!IMPORTANT]
>  Pour éviter certains types de problèmes de sécurité, assurez\-vous que `format` n’est pas une chaîne définie par l’utilisateur. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!NOTE]
>  Pour laisser suffisamment d’espace pour le caractère null de fin quand `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` et `_vsnwprintf_l` sont appelés, vérifiez que `count` est strictement inférieur à la longueur de la mémoire tampon et initialisez la mémoire tampon sur la valeur Null avant d’appeler la fonction.  
>   
>  Étant donné que `vsnprintf` écrit toujours le caractère null de fin, le `count` paramètre peut être égal à la taille de la mémoire tampon.  
  
 Depuis le composant UCRT dans Visual Studio 2015 et Windows 10, `vsnprintf` n’est plus identique à `_vsnprintf`. Le `vsnprintf` fonction conforme à la norme C99 ; `_vnsprintf` est conservée pour compatibilité descendante avec l’ancien code Visual Studio.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_vsntprintf`|`_vsnprintf`|`_vsnprintf`|`_vsnwprintf`|  
|`_vsntprintf_l`|`_vsnprintf_l`|`_vsnprintf_l`|`_vsnwprintf_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis \(C\)|En\-tête requis \(C\+\+\)|  
|-------------|---------------------------|-------------------------------|  
|`vsnprintf`, `_vsnprintf`, `_vsnprintf_l`|\<stdio.h\>|\<stdio.h\> ou \<cstdio\>|  
|`_vsnwprintf`, `_vsnwprintf_l`|\<stdio.h\> ou \<wchar.h\>|\<stdio.h\>, \<wchar.h\>, \<cstdio\> ou \<cwchar\>|  
  
 Les fonctions `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` et `_vsnwprintf_l` sont des fonctions fournies par Microsoft. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```c  
// crt_vsnwprintf.c  
// compile by using: cl /W3 crt_vsnwprintf.c  
  
// To turn off error C4996, define this symbol:  
#define _CRT_SECURE_NO_WARNINGS  
  
#include <stdio.h>  
#include <wtypes.h>  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(LPCWSTR formatstring, ...)  
{  
    int nSize = 0;  
    wchar_t buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead  
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996  
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput(L"%ls %ls", L"Hi", L"there");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");  
}  
```  
  
```Output  
nSize : 8, polissage : Bonjour nSize là : 9, polissage : Bonjour il ! nSize : -1, polissage : Bonjour il !  
```  
  
 Les changements de comportement si vous utilisez vsnprintf à la place, ainsi que les paramètres de chaîne étroite. Le `count` paramètre peut être la taille totale de la mémoire tampon et la valeur de retour est le nombre de caractères qui aurait été écrite si `count` était suffisante :  
  
## Exemple  
  
```c  
// crt_vsnprintf.c  
// compile by using: cl /W4 crt_vsnprintf.c  
#include <stdio.h>  
#include <stdarg.h> // for va_list, va_start  
#include <string.h> // for memset  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(char* formatstring, ...)  
{  
    int nSize = 0;  
    char buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);  
    printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null  
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null  
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null  
}  
```  
  
```Output  
nSize : 8, polissage : Bonjour nSize là : 9, polissage : Bonjour il ! nSize : 10, polissage : Bonjour il !  
```  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)