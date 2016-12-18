---
title: "strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft Docs"
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
  - "_mbstok_l"
  - "_mbstok"
  - "wcstok"
  - "_mbstok"
  - "strtok"
  - "_wcstok_l"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstok"
  - "strtok"
  - "_tcstok"
  - "wcstok"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstok (fonction)"
  - "_mbstok_l (fonction)"
  - "_strtok_l (fonction)"
  - "_tcstok (fonction)"
  - "_tcstok_l (fonction)"
  - "_wcstok_l (fonction)"
  - "mbstok (fonction)"
  - "mbstok_l (fonction)"
  - "chaînes (C++), rechercher"
  - "strtok (fonction)"
  - "strtok_l (fonction)"
  - "tcstok (fonction)"
  - "tcstok_l (fonction)"
  - "jetons, rechercher dans les chaînes"
  - "wcstok (fonction)"
  - "wcstok_l (fonction)"
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
caps.latest.revision: 34
caps.handback.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherche l'unité lexicale suivant dans une chaîne, avec les paramètres régionaux actuels ou des paramètres régionaux spécifiés qui sont passés.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [strtok\_s, \_strtok\_s\_l, wcstok\_s, \_wcstok\_s\_l, \_mbstok\_s, \_mbstok\_s\_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).  
  
> [!IMPORTANT]
>  `_mbstok` et `_mbstok_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `strToken`  
 Chaîne contenant une ou plusieurs unités lexicales.  
  
 `strDelimit`  
 Ensemble de caractères délimiteurs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne un pointeur vers l'unité lexicale suivante trouvée dans `strToken`.  Ils retournent la valeur `NULL` lorsque plus aucune unité lexicale n'est détectée.  Chaque appel change `strToken` en substituant un caractère `NULL` pour le premier séparateur qui arrive après l'unité lexicale retournée.  
  
## Notes  
 La fonction `strtok` recherche l'unité lexicale suivante dans `strToken`.  Le jeu de caractères dans `strDelimit` spécifie les séparateurs possibles de l'unité lexicale à rechercher dans `strToken` sur l'appel actif.  `wcstok` et `_mbstok` sont des versions à caractères élargis et à caractères multi\-octets de `strtok`.  Les arguments et la valeur de retour de `wcstok` sont des chaînes à caractères larges ; ceux de `_mbstok` sont des chaînes de caractères multioctets.  Ces trois fonctions se comportent sinon de façon identique.  
  
> [!IMPORTANT]
>  Ces fonctions entraînent un risque potentiel provoqué par un dépassement de mémoire tampon.  Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Au premier appel de `strtok` la fonction ignore les séparateurs initiaux et retourne un pointeur vers la première unité lexicale de `strToken`, terminant l'unité lexicale avec un caractère Null.  Plus d'unités lexicales peuvent être séparées du reste de `strToken` par une série d'appels à `strtok`.  Chaque appel à `strtok`change`strToken` en insérant un caractère Null après le `token` retourné par cet appel.  Pour lire l'unité lexicale suivante de `strToken`, appelez `strtok` avec une valeur `NULL` pour l'argument `strToken`.  L'argument `strToken` `NULL` force `strtok` à rechercher l'unité lexicale suivante dans le `strToken`modifié.  L'argument `strDelimit` peut prendre n'importe quelle valeur d'un appel au suivant afin que l'ensemble des séparateurs puisse varier.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  Chaque fonction utilise une variable statique de thread local pour décomposer la chaîne en unités lexicales.  Par conséquent, plusieurs threads peuvent simultanément appeler ces fonctions sans effets indésirables.  Toutefois, dans un thread unique, des appels entrelacés à une de ces fonctions risque fortement de produire des données endommagées et des résultats inexacts.  En analysant différentes chaînes, terminez d'analyser une chaîne avant de commencer à analyser la suivante.  En outre, soyez conscient d'un risque potentiel en appelant l'une de ces fonctions depuis une boucle où une autre fonction est appelée.  Si l'autre fonction se termine avec l'une de ces fonctions, une séquence entrelacée d'appels est générée, déclenchant des données endommagées.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcstok`|`strtok`|`_mbstok`|`wcstok`|  
|`_tcstok`|`_strtok_l`|`_mbstok_l`|`_wcstok_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strtok`|\<string.h\>|  
|`wcstok`|\<string.h\> ou \<wchar.h\>|  
|`_mbstok`, `_mbstok_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
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
  
  **Tokens:**  
 **A**  
 **string**  
 **sur**  
 **tokens**  
 **et**  
 **some**  
 **more**  
 **tokens**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)