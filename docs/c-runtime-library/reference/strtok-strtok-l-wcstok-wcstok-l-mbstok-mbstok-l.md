---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs:
- C++
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
caps.latest.revision: 34
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
ms.openlocfilehash: 07948b7fc08bbc41e2e899e190842be98746aeab
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
Recherche le prochain jeton dans une chaîne en utilisant les paramètres régionaux actifs ou les paramètres régionaux spécifiés qui ont été transmis. Il existe des versions plus sécurisées de ces fonctions. Consultez [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).  
  
> [!IMPORTANT]
>  `_mbstok` et `_mbstok_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *strtok(  
   char *strToken,  
   const char *strDelimit   
);  
wchar_t *wcstok(  
   wchar_t *strToken,  
   const wchar_t *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `strToken`  
 Chaîne contenant le ou les jetons.  
  
 `strDelimit`  
 Jeu de caractères délimiteurs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur désignant le prochain jeton trouvé dans `strToken`. `NULL` est retourné dès que plus aucun jeton n’est trouvé. Chaque appel modifie `strToken` en remplaçant un caractère `NULL` par le premier délimiteur qui est trouvé après le jeton retourné.  
  
## <a name="remarks"></a>Notes  
 La fonction `strtok` recherche le prochain jeton dans `strToken`. Le jeu de caractères dans `strDelimit` spécifie les délimiteurs possibles du jeton à rechercher dans `strToken` lors de l’appel en cours. `wcstok` et `_mbstok` sont des versions à caractères larges et à caractères multioctets de `strtok`. Les arguments et la valeur de retour de `wcstok` sont des chaînes de caractères larges ; ceux de `_mbstok` sont des chaînes de caractères multioctets. Ces trois fonctions se comportent sinon de façon identique.  
  
> [!IMPORTANT]
>  Ces fonctions sont exposées à une menace potentielle liée à un problème de dépassement de mémoire tampon. Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Au premier appel de `strtok`, la fonction ignore les délimiteurs de début et retourne un pointeur désignant le premier jeton dans `strToken`, faisant terminer le jeton par un caractère Null. D’autres jetons peuvent être tirés du reste de `strToken` par une série d’appels à `strtok`. Chaque appel à `strtok` modifie `strToken` en insérant un caractère null après le `token` retourné par cet appel. Pour lire le prochain jeton à partir de `strToken`, appelez `strtok` en spécifiant une valeur `NULL` pour l’argument `strToken`. L’argument `strToken` `NULL` contraint `strtok` à rechercher le prochain jeton dans le `strToken` modifié. L’argument `strDelimit` peut prendre n’importe quelle valeur d’un appel à l’autre, si bien que le jeu de délimiteurs peut varier.  
  
 La valeur de sortie est affectée par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  Chaque fonction utilise une variable statique locale de thread pour analyser la chaîne en jetons. Par conséquent, plusieurs threads peuvent appeler simultanément ces fonctions sans effets indésirables. Cependant, dans un thread unique, il est très probable que l’entrelacement d’appels dans l’une de ses fonctions se traduise par une altération des données et des résultats imprécis. Quand il s’agit d’analyser différentes chaînes, terminez l’analyse d’une chaîne avant de débuter celle de la suivante. De même, tenez compte du risque potentiel que représente l’appel de l’une de ces fonctions dans une boucle pendant qu’une autre fonction est appelée. S l’une de ces fonctions met fin à l’autre fonction, une séquence entrelacée d’appels est générée, ce qui a pour conséquence d’altérer les données.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok`|`strtok`|`_mbstok`|`wcstok`|  
|`_tcstok`|`_strtok_l`|`_mbstok_l`|`_wcstok_l`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strtok`|\<string.h>|  
|`wcstok`|\<string.h> ou \<wchar.h>|  
|`_mbstok`, `_mbstok_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_strtok.c  
// compile with: /W3  
// In this program, a loop uses strtok  
// to print all the tokens (separated by commas  
// or blanks) in the string named "string".  
//  
#include <string.h>  
#include <stdio.h>  
  
char string[] = "A string\tof ,,tokens\nand some  more tokens";  
char seps[]   = " ,\t\n";  
char *token;  
  
int main( void )  
{  
   printf( "Tokens:\n" );  
  
   // Establish string and get the first token:  
   token = strtok( string, seps ); // C4996  
   // Note: strtok is deprecated; consider using strtok_s instead  
   while( token != NULL )  
   {  
      // While there are tokens in "string"  
      printf( " %s\n", token );  
  
      // Get next token:   
      token = strtok( NULL, seps ); // C4996  
   }  
}  
```  
  
```Output  
Tokens:  
 A  
 string  
 of  
 tokens  
 and  
 some  
 more  
 tokens  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
