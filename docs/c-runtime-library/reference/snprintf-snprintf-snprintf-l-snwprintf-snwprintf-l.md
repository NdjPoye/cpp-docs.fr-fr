---
title: "snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l | Microsoft Docs"
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
  - "_snwprintf"
  - "_snprintf"
  - "_snprintf_l"
  - "_snwprintf_l"
  - "snprintf"
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
  - "_snprintf"
  - "snprintf_l"
  - "snwprintf_l"
  - "sntprintf"
  - "snprintf"
  - "_sntprintf"
  - "_sntprintf_l"
  - "sntprintf_l"
  - "snwprintf"
  - "_snprintf_l"
  - "_snwprintf"
  - "_snwprintf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "snwprintf_l (fonction)"
  - "sntprintf_l (fonction)"
  - "snprintf_l (fonction)"
  - "_snwprintf_l (fonction)"
  - "_sntprintf_l (fonction)"
  - "_snwprintf (fonction)"
  - "_snprintf (fonction)"
  - "_sntprintf (fonction)"
  - "_snprintf_l (fonction)"
  - "snwprintf (fonction)"
  - "snprintf (fonction)"
  - "sntprintf (fonction)"
  - "texte mis en forme (C++)"
ms.assetid: 5976c9c8-876e-4ac9-a515-39f3f7fd0925
caps.latest.revision: 35
caps.handback.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit des données mises en forme dans une chaîne. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).  
  
## Syntaxe  
  
```  
int snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _snwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
);  
int _snwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int _snprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour la sortie.  
  
 `count`  
 Nombre maximal de caractères à stocker.  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 Laissez `len` être de la longueur de la chaîne de données mise en forme, à l'exclusion de la marque de fin null.`len` et `count` sont tous deux en octets pour `snprintf` et `_snprintf`, caractères larges pour `_snwprintf`.  
  
 Pour toutes les fonctions, si `len` \< `count`, `len` caractères sont stockés dans `buffer`, une marque de fin null est ajoutée, et `len` est retourné.  
  
 La fonction `snprintf` tronque le résultat quand `len` est supérieur ou égal à `count`, en plaçant une marque de fin null au niveau de `buffer[count-1]`. La valeur retournée est `len`, le nombre de caractères produits si `count` était assez important. La fonction `snprintf` retourne une valeur négative en cas d’erreur de codage.  
  
 Pour toutes les fonctions autres que `snprintf`, si `len` \= `count`, `len` caractères sont stockés dans `buffer`, aucune marque de fin null n’est ajoutée, et `len` est retourné. Si `len` \> `count`, les caractères `count` sont stockés dans `buffer`, aucune marque de fin null n'est ajoutée, et une valeur négative est retournée.  
  
 Si `buffer` est un pointeur null et `count` est égal à zéro, `len` est retourné comme nombre de caractères requis pour mettre en forme la sortie, à l'exception de la marque de fin null. Pour effectuer un appel réussi avec le même `argument` et les paramètres `locale`, allouez une mémoire tampon contenant au moins `len` \+ 1 caractères.  
  
 Si `buffer` est un pointeur null et `count` est différent de zéro, ou si `format` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et définissent `errno` avec la valeur `EINVAL`.  
  
 Pour plus d’informations sur ces codes et d’autres codes d’erreur, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `snprintf` et la famille de fonctions `_snprintf` mettent en forme et stockent `count` caractères au maximum dans `buffer`. La fonction `snprintf` stocke toujours un caractère null de fin et tronque la sortie si nécessaire. La famille de fonctions `_snprintf` ajoute uniquement un caractère null de fin si la longueur de la chaîne mise en forme est strictement inférieure à `count` caractères. Chaque `argument` \(le cas échéant\) est converti et sorti selon la spécification de format correspondante dans `format`. Le format se compose de caractères ordinaires et a la même forme et fonction que l'argument `format` pour [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Si une copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur. Les fonctions `_snprintf` ne garantissant pas la marque de fin NULL, en particulier quand la valeur de retour est `count`, vérifiez qu’elles sont suivies du code qui ajoute la marque de fin null. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Depuis le composant UCRT dans Visual Studio 2015 et Windows 10, `snprintf` n’est plus identique à `_snprintf`. Le comportement de la fonction `snprintf` est désormais conforme à la norme C99.  
  
 `_snwprintf` est une version à caractères larges de `_snprintf` ; les arguments de pointeur de `_snwprintf` sont des chaînes à caractères larges. La détection d'erreurs d'encodage dans `_snwprintf` peut différer de celle dans `_snprintf`.`_snwprintf`, tout comme `swprintf`, écrit la sortie dans une chaîne au lieu d'une destination de type `FILE`.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_sntprintf`|`_snprintf`|`_snprintf`|`_snwprintf`|  
|`_sntprintf_l`|`_snprintf_l`|`_snprintf_l`|`_snwprintf_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`snprintf`, `_snprintf`,  `_snprintf_l`|\<stdio.h\>|  
|`_snwprintf`, `_snwprintf_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```c  
// crt_snprintf.c  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
#if !defined(__cplusplus)  
typedef int bool;  
const bool true = 1;  
const bool false = 0;  
#endif  
  
#define FAIL 0 // change to 1 and see what happens  
  
int main(void)  
{  
   char buffer[200];  
   const static char s[] = "computer"  
#if FAIL  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
#endif  
   ;  
   const char c = 'l';   
   const int i = 35;  
#if FAIL  
   const double fp = 1e300; // doesn't fit in the buffer  
#else  
   const double fp = 1.7320534;  
#endif  
   /* !subtract one to prevent "squeezing out" the terminal nul! */  
   const int bufferSize = sizeof(buffer)/sizeof(buffer[0]) - 1;  
   int bufferUsed = 0;  
   int bufferLeft = bufferSize - bufferUsed;  
   bool bSuccess = true;  
   buffer[0] = 0;  
  
   /* Format and print various data: */  
  
   if (bufferLeft > 0)  
   {  
      int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
      bufferLeft, "   String: %s\n", s ); // C4996  
      // Note: _snprintf is deprecated; consider _snprintf_s instead  
      if (bSuccess = (perElementBufferUsed >= 0))  
      {  
         bufferUsed += perElementBufferUsed;  
         bufferLeft -= perElementBufferUsed;  
         if (bufferLeft > 0)  
         {  
            int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
            bufferLeft, "   Character: %c\n", c ); // C4996  
            if (bSuccess = (perElementBufferUsed >= 0))  
            {  
               bufferUsed += perElementBufferUsed;  
               bufferLeft -= perElementBufferUsed;  
               if (bufferLeft > 0)  
               {  
                  int perElementBufferUsed = _snprintf(&buffer  
                  [bufferUsed], bufferLeft, "   Integer: %d\n", i ); // C4996  
                  if (bSuccess = (perElementBufferUsed >= 0))  
                  {  
                     bufferUsed += perElementBufferUsed;  
                     bufferLeft -= perElementBufferUsed;  
                     if (bufferLeft > 0)  
                     {  
                        int perElementBufferUsed = _snprintf(&buffer  
                        [bufferUsed], bufferLeft, "   Real: %f\n", fp ); // C4996  
                        if (bSuccess = (perElementBufferUsed >= 0))  
                        {  
                           bufferUsed += perElementBufferUsed;  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
   }  
  
   if (!bSuccess)  
   {  
      printf("%s\n", "failure");  
   }  
   else  
   {  
      /* !store nul because _snprintf doesn't necessarily (if the string   
       * fits without the terminal nul, but not with it)!  
       * bufferUsed might be as large as bufferSize, which normally is   
       * like going one element beyond a buffer, but in this case   
       * subtracted one from bufferSize, so we're ok.  
       */  
      buffer[bufferUsed] = 0;  
      printf( "Output:\n%s\ncharacter count = %d\n", buffer, bufferUsed );  
   }  
   return EXIT_SUCCESS;  
}  
```  
  
```Output  
Output: String: computer Character: l Integer: 35 Real: 1.732053 character count = 69  
```  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)