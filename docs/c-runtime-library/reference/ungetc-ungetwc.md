---
title: ungetc, ungetwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ungetwc
- ungetc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ungettc
- ungetwc
- ungetc
dev_langs:
- C++
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 3bab0bd81a8a17fd32c244bab0dd30658564d257
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc
Renvoie un caractère dans le flux via une transmission de type push.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractère à renvoyer (transmission push).  
  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 Si réussite, chacune de ces fonctions retourne l’argument de caractère `c`. Si `c` ne peut pas être renvoyé via une transmission de type push ou si aucun caractère n’a été lu, le flux d’entrée est inchangé et `ungetc` retourne `EOF` ; `ungetwc` retourne `WEOF`. Si `stream` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `EOF` ou `WEOF` est retourné et `errno` prend la valeur `EINVAL`.  
  
 Pour obtenir des informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `ungetc` renvoie le caractère `c` à `stream` via une transmission de type push et efface l’indicateur de fin de fichier. Le flux doit être ouvert pour lecture. Opération de lecture suivante sur `stream` commence par `c`. Une tentative de transmission de type push de `EOF` vers le flux à l’aide de `ungetc` est ignorée.  
  
 Les caractères positionnés dans le flux par `ungetc` peuvent être effacés si la fonction `fflush`, `fseek`, `fsetpos` ou `rewind` est appelée avant que le caractère soit lu dans le flux. L’indicateur de position de fichier prend alors la valeur qui était la sienne avant que les caractères soient renvoyés via la transmission push. Le stockage externe correspondant au flux est inchangé. Si l’appel de la fonction `ungetc` pour un flux de texte aboutit, l’indicateur de position de fichier n’est pas spécifié tant que tous les caractères renvoyés via une transmission push ne sont pas lus ou ignorés. À chaque appel réussi de la fonction `ungetc` sur un flux binaire, l’indicateur de position de fichier est décrémenté ; si sa valeur était égale à 0 avant un appel, la valeur est indéfinie après l’appel.  
  
 Les résultats sont imprévisibles si la fonction `ungetc` est appelée à deux reprises sans qu’aucune opération de lecture ou de positionnement de fichier n’ait lieu entre les deux appels. Après un appel à la fonction `fscanf`, un appel à `ungetc` peut échouer si une autre opération de lecture (telle que `getc`) n’a pas été exécutée. Cela est dû au fait que la fonction `fscanf` elle-même appelle `ungetc`.  
  
 `ungetwc` est une version à caractères larges de `ungetc`. Cependant, à chaque appel réussi de la fonction `ungetwc` sur un flux de texte ou binaire, la valeur de l’indicateur de position de fichier n’est pas spécifié tant que tous les caractères renvoyés via une transmission push ne sont pas lus ou ignorés.  
  
 Ces fonctions sont thread-safe et verrouillent les données sensibles pendant l’exécution. Pour une version sans verrouillage, consultez [_ungetc_nolock, _ungetwc_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`ungetc`|\<stdio.h>|  
|`ungetwc`|\<stdio.h> ou \<wchar.h>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] . Les handles de flux standard associés à la console (`stdin`, `stdout` et `stderr`) doivent être redirigés pour que les fonctions Runtime C puissent les utiliser dans les applications du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
```Output  
  
      521aNumber = 521  
Next character in stream = 'a'  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)