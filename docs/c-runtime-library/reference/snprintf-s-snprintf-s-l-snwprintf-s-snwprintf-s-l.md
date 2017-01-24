---
title: "_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l | Microsoft Docs"
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
  - "_snprintf_s"
  - "_snprintf_s_l"
  - "_snwprintf_s"
  - "_snwprintf_s_l"
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
  - "_snwprintf_s_l"
  - "_sntprintf_s_l"
  - "snprintf_s_l"
  - "_snprintf_s_l"
  - "_sntprintf_s"
  - "_snprintf_s"
  - "snprintf_s"
  - "_snwprintf_s"
  - "snwprintf_s_l"
  - "snwprintf_s"
  - "sntprintf_s"
  - "sntprintf_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_snprintf_s (fonction)"
  - "_snprintf_s_l (fonction)"
  - "_sntprintf_s (fonction)"
  - "_sntprintf_s_l (fonction)"
  - "_snwprintf_s (fonction)"
  - "_snwprintf_s_l (fonction)"
  - "texte mis en forme (C++)"
  - "snprintf_s (fonction)"
  - "snprintf_s_l (fonction)"
  - "sntprintf_s (fonction)"
  - "sntprintf_s_l (fonction)"
  - "snwprintf_s (fonction)"
  - "snwprintf_s_l (fonction)"
ms.assetid: 9336ab86-13e5-4a29-a3cd-074adfee6891
caps.latest.revision: 32
caps.handback.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit des données mises en forme dans une chaîne. Voici les versions de [snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) avec des améliorations de sécurité comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int _snprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _snwprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
);  
int _snwprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int _snprintf_s(  
   char (&buffer)[size],  
   size_t count,  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf_s(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour la sortie.  
  
 `sizeOfBuffer`  
 La taille de l’emplacement de stockage pour la sortie. Taille de `bytes` de `_snprintf_s` ou de taille dans `words` pour `_snwprintf_s`.  
  
 `Count`  
 Nombre maximal de caractères à stocker, ou [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_snprintf_s` Retourne le nombre de caractères stockés dans `buffer`, sans compter le caractère null de fin.`_snwprintf_s` retourne le nombre de caractères larges stockés dans `buffer`, sans compter le caractère large null de fin.  
  
 Si le stockage nécessaire au stockage des données et un caractère null de fin dépasse `sizeOfBuffer`, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution se poursuit après le Gestionnaire de paramètre non valide, ces fonctions définissent `buffer` une chaîne vide, définissez `errno` à `ERANGE`, et retournent \-1.  
  
 Si `buffer` ou `format` est un `NULL` pointeur, ou si `count` est inférieur ou égal à zéro, le Gestionnaire de paramètre non valide est appelé. Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1.  
  
 Pour plus d'informations sur ces codes d'erreur et les autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Le `_snprintf_s` formats de fonction et les magasins `count` caractères au maximum dans `buffer` et ajoute un caractère null de fin. Chaque argument \(le cas échéant\) est converti et sorti selon la spécification de format correspondante dans `format`. La mise en forme est cohérent avec la `printf` famille de fonctions ; consultez [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). Si une copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
 Si `count` est [\_TRUNCATE](../../c-runtime-library/truncate.md), puis `_snprintf_s` écritures autant de la chaîne selon tenir dans `buffer` tout en laissant la place pour un caractère null de fin. Si la chaîne entière \(avec le caractère null de fin\) s’intègre à `buffer`, puis `_snprintf_s` renvoie le nombre de caractères écrits \(non compris le caractère null de fin\) ; sinon, `_snprintf_s` retourne \-1 pour indiquer que la troncation s’est produite.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
 `_snwprintf_s` est une version à caractères larges de `_snprintf_s` ; les arguments de pointeur de `_snwprintf_s` sont des chaînes à caractères larges. La détection d'erreurs d'encodage dans `_snwprintf_s` peut différer de celle dans `_snprintf_s`.`_snwprintf_s`, comme `swprintf_s`, écrit la sortie vers une chaîne plutôt que vers une destination de type `FILE`.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 En C\+\+, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d’avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_sntprintf_s`|`_snprintf_s`|`_snprintf_s`|`_snwprintf_s`|  
|`_sntprintf_s_l`|`_snprintf_s_l`|`_snprintf_s_l`|`_snwprintf_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_snprintf_s`, `_snprintf_s_l`|\<stdio.h\>|  
|`_snwprintf_s`, `_snwprintf_s_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_snprintf_s.cpp  
// compile with: /MTd  
  
// These #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
int snprintf_s_tester( const char * fmt, int x, size_t count )  
{  
   char dest[10];  
  
   printf( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf( "%zd-byte buffer; truncation semantics\n",  
               _countof(dest) );  
   else  
      printf( "count = %zd; %zd-byte buffer\n",  
               count, _countof(dest) );  
  
   int ret = _snprintf_s( dest, _countof(dest), count, fmt, x );  
  
   printf( "    new contents of dest: '%s'\n", dest );  
  
   return ret;  
}  
  
void Examples()  
{  
   // formatted output string is 9 characters long: "<<<123>>>"  
   snprintf_s_tester( "<<<%d>>>", 121, 8 );  
   snprintf_s_tester( "<<<%d>>>", 121, 9 );  
   snprintf_s_tester( "<<<%d>>>", 121, 10 );  
  
   printf( "\nDestination buffer too small:\n" );  
  
   snprintf_s_tester( "<<<%d>>>", 1221, 10 );  
  
   printf( "\nTruncation examples:\n" );  
  
   int ret = snprintf_s_tester( "<<<%d>>>", 1221, _TRUNCATE );  
   printf( "    truncation %s occur\n", ret == -1 ? "did"  
                                                  : "did not" );  
  
   ret = snprintf_s_tester( "<<<%d>>>", 121, _TRUNCATE );  
   printf( "    truncation %s occur\n", ret == -1 ? "did"  
                                                  : "did not" );  
   printf( "\nSecure template overload example:\n" );  
  
   char dest[10];  
   _snprintf( dest, 10, "<<<%d>>>", 12321 );  
   // With secure template overloads enabled (see #defines  
   // at top of file), the preceding line is replaced by  
   //    _snprintf_s( dest, _countof(dest), 10, "<<<%d>>>", 12345 );  
   // Instead of causing a buffer overrun, _snprintf_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, _snprintf would  
   // write 10 characters and overrun the dest buffer.  
   printf( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
```Output  
  
nombre = 8 ; nouveau contenu de tampon de 10 octets de dest : ' <<< 121 >> ' count = 9 ; nouveau contenu de tampon de 10 octets de dest : '<<< 121 >>> ' count = 10 ; nouveau contenu de tampon de 10 octets de dest : '<<< 121 >>> ' tampon de Destination trop petit : nombre = 10 ; Gestionnaire de paramètre non valide de tampon de 10 octets appelé : (« Tampon trop petit », 0) nouveau contenu de destination : « exemples de troncation : tampon de 10 octets ; troncation sémantique nouveau contenu de dest : ' <<< 1221 >> ' troncation s’est produite le tampon de 10 octets ; troncation sémantique nouveau contenu de dest : troncation de '<<< 121 >>> ' ne prenaient pas exemple surcharge de modèle sécurisées : Gestionnaire de paramètre non valide appelé : (« Tampon trop petit », 0) nouveau contenu de dest : ''  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)