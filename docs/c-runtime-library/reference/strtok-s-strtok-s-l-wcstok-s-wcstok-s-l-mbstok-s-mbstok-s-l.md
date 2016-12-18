---
title: "strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Microsoft Docs"
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
  - "_wcstok_s_l"
  - "_mbstok_s_l"
  - "_mbstok_s"
  - "strtok_s"
  - "wcstok_s"
  - "_strtok_s_l"
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
  - "_tcstok_s_l"
  - "_wcstok_s_l"
  - "_tcstok_s"
  - "_mbstok_s_l"
  - "strtok_s"
  - "wcstok_s"
  - "_mbstok_s"
  - "_strtok_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstok_s (fonction)"
  - "_mbstok_s_l (fonction)"
  - "_strtok_s_l (fonction)"
  - "_tcstok_s (fonction)"
  - "_tcstok_s_l (fonction)"
  - "_wcstok_s_l (fonction)"
  - "mbstok_s (fonction)"
  - "mbstok_s_l (fonction)"
  - "chaînes (C++), rechercher"
  - "strtok_s (fonction)"
  - "strtok_s_l (fonction)"
  - "jetons, rechercher dans les chaînes"
  - "wcstok_s (fonction)"
  - "wcstok_s_l (fonction)"
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherche le jeton suivant dans une chaîne, en utilisant les paramètres régionaux actuels ou des paramètres régionaux qui sont passés.  Ces versions [strtok, \_strtok\_l, wcstok, \_wcstok\_l, \_mbstok, \_mbstok\_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbstok_s` et `_mbstok_s_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
  
      char *strtok_s(  
char *strToken,  
const char *strDelimit,  
   char **context  
);  
char *_strtok_s_l(  
char *strToken,  
const char *strDelimit,  
   char **context,  
_locale_tlocale  
);  
wchar_t *wcstok_s(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context  
);  
wchar_t *_wcstok_s_l(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context,  
_locale_tlocale  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context,  
_locale_tlocale  
);  
```  
  
#### Paramètres  
 `strToken`  
 Chaîne contenant un ou plusieurs jetons.  
  
 `strDelimit`  
 Ensemble de caractères délimiteurs.  
  
 `context`  
 Utilisé pour stocker les informations de position entre les appels à `strtok_s`  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne un pointeur vers le jeton suivant trouvé dans `strToken`.  Ils retournent la valeur `NULL` lorsque plus aucun jeton n'est détecté.  Chaque appel change `strToken` en substituant un caractère `NULL` au premier séparateur qui se produit après que le jeton soit retourné.  
  
### Conditions d'erreur  
  
|`strToken`|`strDelimit`|`context`|Valeur de retour|`errno`|  
|----------------|------------------|---------------|----------------------|-------------|  
|`NULL`|any|pointeur vers un pointeur null|`NULL`|`EINVAL`|  
|any|`NULL`|any|`NULL`|`EINVAL`|  
|any|any|`NULL`|`NULL`|`EINVAL`|  
  
 Si `strToken` est `NULL` mais le contexte est un pointeur vers un pointeur valide de contexte, il n'y a aucune erreur.  
  
## Notes  
 La fonction `strtok_s` recherche le jeton suivant dans `strToken`.  Le jeu de caractères de `strDelimit` spécifie les séparateurs possibles du jeton à rechercher dans `strToken` sur l'appel actif.  `wcstok_s` et `_mbstok_s`sont des versions à caractères élargis et à caractères multi\-octets de `strtok_s`.  Les arguments et les valeurs de retour de `wcstok_s` et de `_wcstok_s_l` sont des chaînes à caractères larges ; ceux de `_mbstok_s` et de `_mbstok_s_l` sont des chaînes de caractères multioctets.  Ces trois fonctions se comportent sinon de façon identique.  
  
 Cette fonction valide ses paramètres.  Si une condition d'erreur apparaît, comme dans la table de conditions d'erreur, le gestionnaire de paramètres invalides est appelé, comme il est décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à la valeur `EINVAL` et retournent `NULL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|  
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|  
  
 Au premier appel à `strtok_s` la fonction ignore des séparateurs et retourne un pointeur vers le premier jeton de `strToken`, terminant le jeton avec un caractère Null.  Plus de jetons peuvent être séparés du reste de `strToken` par une série d'appels à `strtok_s`.  Chaque appel à `strtok_s` change `strToken` en insérant un caractère Null après le jeton retourné par cet appel.  Le pointeur `context` garde la trace des chaînes étant lues et où dans la chaîne le jeton suivant doit être lu.  Pour lire le jeton suivant de `strToken`, appelez `strtok_s` avec une valeur `NULL` pour l'argument `strToken`, puis passez le paramètre `context`.  L'argument `strToken` `NULL` force `strtok_s` à rechercher le jeton suivant dans le `strToken`modifié.  L'argument `strDelimit` peut prendre n'importe quelle valeur d'un appel au suivant afin que l'ensemble des séparateurs puisse varier.  
  
 Puisque le paramètre `context` remplace les mémoires tampons statiques utilisés dans `strtok` et `_strtok_l`, il est possible d'analyser deux chaînes simultanément dans le même thread.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strtok_s`|\<string.h\>|  
|`_strtok_s_l`|\<string.h\>|  
|`wcstok_s,`<br /><br /> `_wcstok_s_l`|\<string.h\> ou \<wchar.h\>|  
|`_mbstok_s,`<br /><br /> `_mbstok_s_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strtok_s.c  
// In this program, a loop uses strtok_s  
// to print all the tokens (separated by commas  
// or blanks) in two strings at the same time.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
char string1[] =  
    "A string\tof ,,tokens\nand some  more tokens";  
char string2[] =  
    "Another string\n\tparsed at the same time.";  
char seps[]   = " ,\t\n";  
char *token1 = NULL;  
char *token2 = NULL;  
char *next_token1 = NULL;  
char *next_token2 = NULL;  
  
int main( void )  
{  
    printf( "Tokens:\n" );  
  
    // Establish string and get the first token:  
    token1 = strtok_s( string1, seps, &next_token1);  
    token2 = strtok_s ( string2, seps, &next_token2);  
  
    // While there are tokens in "string1" or "string2"  
    while ((token1 != NULL) || (token2 != NULL))  
    {  
        // Get next token:  
        if (token1 != NULL)  
        {  
            printf( " %s\n", token1 );  
            token1 = strtok_s( NULL, seps, &next_token1);  
        }  
        if (token2 != NULL)  
        {  
            printf("        %s\n", token2 );  
            token2 = strtok_s (NULL, seps, &next_token2);  
        }  
    }  
}  
```  
  
  **Tokens:**  
 **A**  
 **Autre**  
 **string**  
 **string**  
 **sur**  
 **analysé**  
 **jetons**  
 **at**  
 **et**  
 **la section**  
 **quelques**  
 **même**  
 **more**  
 **au temps.**  
 **jetons**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)