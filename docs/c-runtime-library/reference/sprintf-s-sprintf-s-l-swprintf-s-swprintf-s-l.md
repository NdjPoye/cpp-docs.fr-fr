---
title: "sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_swprintf_s_l"
  - "_sprintf_s_l"
  - "swprintf_s"
  - "sprintf_s"
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
  - "swprintf_s"
  - "sprintf_s"
  - "stdio/sprintf_s"
  - "stdio/swprintf_s"
  - "stdio/_sprintf_s_l"
  - "stdio/_swprintf_s_l"
  - "_sprintf_s_l"
  - "_swprintf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stprintf_s (fonction)"
  - "stprintf_s_l (fonction)"
  - "swprintf_s_l (fonction)"
  - "sprintf_s (fonction)"
  - "swprintf_s (fonction)"
  - "_swprintf_s_l (fonction)"
  - "sprintf_s_l (fonction)"
  - "_stprintf_s_l (fonction)"
  - "_stprintf_s (fonction)"
  - "_sprintf_s_l (fonction)"
  - "texte mis en forme (C++)"
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrire des données mises en forme dans une chaîne. Il s’agit de versions de [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int sprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   ...   
);  
int _sprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale,  
   ...   
);  
int swprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   ...  
);  
int _swprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale,  
   ...  
);  
template <size_t size>  
int sprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   ...   
); // C++ only  
template <size_t size>  
int swprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   ...  
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour la sortie  
  
 `sizeOfBuffer`  
 Nombre maximal de caractères à stocker.  
  
 `format`  
 Chaîne de contrôle de format  
  
 `...`  
 Arguments facultatifs de mise en forme  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 Nombre de caractères écrits, ou –1 si une erreur s'est produite. Si `buffer` ou `format` est un pointeur null, `sprintf_s` et `swprintf_s` retournent \-1 et affectent la valeur `errno` à `EINVAL`.  
  
 `sprintf_s` retourne le nombre d'octets stockés dans `buffer`, sans compter le caractère null de fin.`swprintf_s` retourne le nombre de caractères larges stockés dans `buffer`, sans compter le caractère large null de fin.  
  
## Notes  
 La fonction `sprintf_s` met en forme une série de caractères et de valeurs et la stocke dans `buffer`. Chaque `argument` \(le cas échéant\) est converti et sorti selon la spécification de format correspondante dans `format`. Le format se compose de caractères ordinaires et a la même forme et fonction que l'argument `format` pour [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Un caractère null est ajouté après le dernier caractère écrit. Si une copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
 L'une des principales différences entre `sprintf_s` et `sprintf` est que `sprintf_s` vérifie si la chaîne de format comporte des caractères de mise en forme valides, tandis que `sprintf` vérifie uniquement si la chaîne de format ou la mémoire tampon est un pointeur `NULL`. Si l’une des vérifications échoue, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, la fonction retourne \-1 et définit `errno` avec la valeur `EINVAL`.  
  
 L'autre différence principale entre `sprintf_s` et `sprintf` est que `sprintf_s` prend un paramètre de longueur spécifiant la taille de la mémoire tampon de sortie en caractères. Si la mémoire tampon est trop petite pour le texte mis en forme, y compris le caractère Null de fin, elle est définie sur une chaîne vide en plaçant un caractère Null à `buffer``[0]`, et le gestionnaire de paramètre non valide est appelé. Contrairement à `_snprintf`, `sprintf_s` garantit que la mémoire tampon se termine par Null, sauf si la taille de la mémoire tampon est égale à zéro.  
  
 `swprintf_s` est une version à caractères larges de `sprintf_s` ; les arguments de pointeur de `swprintf_s` sont des chaînes à caractères larges. La détection d'erreurs d'encodage dans `swprintf_s` peut différer de celle dans `sprintf_s`. Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 En C\+\+, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle. Les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement, ce qui évite d’avoir à spécifier un argument taille, et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Il existe des versions de `sprintf_s` qui offrent un contrôle supplémentaire sur ce qui se produit si la mémoire tampon est trop petite. Pour plus d'informations, consultez [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_stprintf_s`|`sprintf_s`|`sprintf_s`|`swprintf_s`|  
|`_stprintf_s_l`|`_sprintf_s_l`|`_sprintf_s_l`|`_swprintf_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`sprintf_s`, `_sprintf_s_l`|C : \<stdio.h\><br /><br /> C\+\+ : \<cstdio\> ou \<stdio.h\>|  
|`swprintf_s`, `_swprintf_s_l`|C : \<stdio.h\> ou \<wchar.h\><br /><br /> C\+\+ : \<cstdio\>, \<cwchar\>, \<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_sprintf_s.c  
// This program uses sprintf_s to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );  
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );  
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );  
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );  
  
   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
}  
```  
  
```Output  
Sortie : String:    computer Character: l Integer:   35 Real:      1.732053 character count = 79  
```  
  
## Exemple  
  
```  
// crt_swprintf_s.c  
// wide character example  
// also demonstrates swprintf_s returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf_s fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
```Output  
wrote 11 characters wrote -1 characters  
```  
  
## Équivalent .NET Framework  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)