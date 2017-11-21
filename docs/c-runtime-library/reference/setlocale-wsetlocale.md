---
title: setlocale, _wsetlocale | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsetlocale
- setlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
dev_langs: C++
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6a86fa0962ab55c8df1bcd81f83d10d92ea8f304
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setlocale-wsetlocale"></a>setlocale, _wsetlocale
Définit ou extrait les paramètres régionaux d'exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *setlocale(  
   int category,  
   const char *locale   
);  
wchar_t *_wsetlocale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `category`  
 Catégorie affectée par les paramètres régionaux.  
  
 `locale`  
 Spécificateur de paramètres régionaux.  
  
## <a name="return-value"></a>Valeur de retour  
 Si des paramètres `locale` et `category` valides sont définis, ils retournent un pointeur vers la chaîne associée aux paramètres `locale` et `category` spécifiés. Si le paramètre `locale` ou `category` n'est pas valide, il retourne un pointeur null et les paramètres régionaux actuels du programme ne sont pas modifiés.  
  
 Par exemple, l'appel  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 définit toutes les catégories, en retournant uniquement la chaîne  
  
 `en-US`  
  
 Vous pouvez copier la chaîne retournée par `setlocale` pour restaurer cette partie des informations relatives aux paramètres régionaux du programme. Un stockage local des threads ou un stockage global est utilisé pour la chaîne retournée par `setlocale`. Les appels ultérieurs à `setlocale` remplacent la chaîne, ce qui rend les pointeurs de chaîne retournés par les appels antérieurs non valides.  
  
## <a name="remarks"></a>Notes  
 Utilisez la fonction `setlocale` pour définir, modifier, ou interroger certaines ou toutes les informations de paramètres régionaux du programme actif spécifié par `locale` et `category`. `locale` fait référence à la localité (pays/région et langue) pour laquelle vous pouvez personnaliser certains aspects du programme. Certaines catégories dépendent des paramètres régionaux, notamment la mise en forme des dates et le format d'affichage des valeurs monétaires. Si vous affectez le paramètre `locale` à la chaîne par défaut pour une langue qui a plusieurs formes prises en charge sur votre ordinateur, vous devrez d'abord vérifier la valeur de retour de `setlocale` pour connaître la langue appliquée. Par exemple, si vous définissez `locale` à « chinois », la valeur de retour peut être « chinois simplifié » ou « chinois traditionnel ».  
  
 `_wsetlocale` est une version à caractères larges de `setlocale`; l'argument `locale` et la valeur de retour de `_wsetlocale` sont des chaînes à caractères larges. Sinon, `_wsetlocale` et `setlocale` se comportent de la même façon.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|  
  
 L'argument `category` spécifie les parties des informations relatives aux paramètres régionaux d'un programme qui sont affectées. Les macros utilisées pour `category` et les parties du programme qu'elles affectent sont les suivantes :  
  
 `LC_ALL`  
 Toutes les catégories de la liste suivante.  
  
 `LC_COLLATE`  
 Les fonctions `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` et `wcsxfrm`.  
  
 `LC_CTYPE`  
 Les fonctions de gestion de caractères (sauf `isdigit`, `isxdigit`, `mbstowcs`, et `mbtowc`, qui ne sont pas affectés).  
  
 `LC_MONETARY`  
 Les informations de mise en forme monétaire retournées par la fonction `localeconv`.  
  
 `LC_NUMERIC`  
 Le caractère de virgule décimale pour les routines de sortie mise en forme (comme `printf`), pour les routines de conversion de données, et pour les informations de mise en forme non monétaire retournées par `localeconv`. En plus du caractère de virgule décimale, `LC_NUMERIC` définit aussi le séparateur des milliers et la chaîne de contrôle de regroupement retournés par [localeconv](../../c-runtime-library/reference/localeconv.md).  
  
 `LC_TIME`  
 Les fonctions `strftime` et `wcsftime`.  
  
 Cette fonction valide le paramètre de catégorie. Si le paramètre de catégorie ne fait pas partie des valeurs fournies dans le tableau précédent, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, la fonction définit `errno` avec la valeur `EINVAL` et retourne `NULL`.  
  
 L'argument `locale` est un pointeur vers une chaîne qui spécifie les paramètres régionaux. Pour plus d’informations sur le format de l’argument `locale`, consultez [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Si `locale` pointe vers une chaîne vide, les paramètres régionaux sont donnés par l'environnement défini lors de l'implémentation. Une valeur de `C` spécifie l'environnement de conformation minimal ANSI pour la conversion en C. Les paramètres régionaux de `C` supposent que tous les types de données de `char` sont de 1 octet et que leur valeur est toujours inférieure à 256.  
  
 Au démarrage du programme, l'équivalent de l'instruction suivante est exécuté :  
  
 `setlocale( LC_ALL, "C" );`  
  
 L'argument `locale` peut accepter un nom de paramètres régionaux, une chaîne de langue, une chaîne de langue et un pays/région, une page de codes, ou une chaîne de langue, un pays/région, et une page de codes. L'ensemble des noms de paramètres régionaux, des langages, des pays ou codes zone, et de pages de codes disponibles inclut tous ceux pris en charge par l'API Windows NLS, à l'exception des pages de codes qui requièrent plus de deux octets par caractère, telles que UTF-7 et UTF-8. Si vous fournissez une page de codes comme UTF-7 ou UTF-8, `setlocale` va échouer, en retournant NULL. L’ensemble des noms de paramètres régionaux pris en charge par `setlocale` est décrit dans [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). L’ensemble des chaînes de langue et de pays/région prises en charge par `setlocale` est répertorié dans [Chaînes de langue](../../c-runtime-library/language-strings.md) et [Chaînes pays/région](../../c-runtime-library/country-region-strings.md). Nous recommandons d'utiliser la forme de nom des paramètres régionaux pour des questions de performance et de maintenance des chaînes de paramètres régionaux incorporées dans le code ou sérialisées du stockage. Les chaînes de nom des paramètres régionaux sont moins susceptibles d'être modifiées par une mise à niveau du système d'exploitation que la forme de nom de la langue et du pays ou de la région.  
  
 Un pointeur null ajouté à l'argument `locale` indique à `setlocale` d'interroger au lieu de définir l'environnement international. Si l'argument `locale` est un pointeur null, les paramètres régionaux actuels du programme ne sont pas modifiés. À la place, `setlocale` retourne un pointeur vers la chaîne associée à l'argument `category` des paramètres régionaux actuels du thread. Si l'argument `category` est `LC_ALL`, la fonction retourne une chaîne qui indique le paramètre actuel de chaque catégorie, séparé par des points-virgules. Par exemple, la séquence d'appels  
  
 `// Set all categories and return "en-US"`  
  
 `setlocale(LC_ALL, "en-US");`  
  
 `// Set only the LC_MONETARY category and return "fr-FR"`  
  
 `setlocale(LC_MONETARY, "fr-FR");`  
  
 `printf("%s\n", setlocale(LC_ALL, NULL));`  
  
 retourne  
  
 `LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US`  
  
 qui est la chaîne associée à la catégorie `LC_ALL`.  
  
 Les exemples suivants appartiennent à la catégorie `LC_ALL`. Les deux chaînes « .OCP » et « .ACP » peuvent être utilisées à la place du numéro de page de codes pour spécifier, respectivement, l'utilisation de la page de codes OEM utilisateur par défaut et la page de codes ANSI utilisateur par défaut.  
  
 `setlocale( LC_ALL, "" );`  
 Définit les paramètres régionaux à la valeur par défaut, qui est la page de codes ANSI utilisateur par défaut obtenue du système d'exploitation.  
  
 `setlocale( LC_ALL, ".OCP" );`  
 Définit explicitement les paramètres régionaux à la page de codes OEM actuelle fournie par le système d'exploitation.  
  
 `setlocale( LC_ALL, ".ACP" );`  
 Définit les paramètres régionaux à la page de codes ANSI fournie par le système d'exploitation.  
  
 `setlocale( LC_ALL, "<localename>" );`  
 Définit les paramètres régionaux en fonction du nom de paramètres régionaux indiqué par *\<localename>*.  
  
 `setlocale( LC_ALL, "<language>_<country>" );`  
 Définit les paramètres régionaux en fonction de la langue et du pays/région indiqués par *\<language>* et *\<country>* et en tenant compte de la page de codes par défaut obtenue du système d’exploitation hôte.  
  
 `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`  
 Définit les paramètres régionaux en fonction de la langue, du pays/région et de la page de codes indiqués par les chaînes *\<language*, *\<country>* et *<code_page>*. Vous pouvez utiliser différentes combinaisons de langues, pays/région et page de codes. Par exemple, cet appel définit les paramètres régionaux à français du Canada avec la page de codes 1252 :  
  
 `setlocale( LC_ALL, "French_Canada.1252" );`  
  
 Cet appel définit les paramètres régionaux à français du Canada avec la page de codes ANSI par défaut :  
  
 `setlocale( LC_ALL, "French_Canada.ACP" );`  
  
 Cet appel définit les paramètres régionaux à français du Canada avec la page de codes OEM par défaut :  
  
 `setlocale( LC_ALL, "French_Canada.OCP" );`  
  
 `setlocale( LC_ALL, "<language>" );`  
 Définit les paramètres régionaux en fonction de la langue indiquée par *\<language>* et utilise le pays/région par défaut de la langue spécifiée et la page de codes ANSI utilisateur par défaut pour le pays/région en question obtenus du système d’exploitation hôte. Par exemple, les appels suivants à `setlocale` sont fonctionnellement équivalents :  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 `setlocale( LC_ALL, "English" );`  
  
 `setlocale( LC_ALL, "English_United States.1252" );`  
  
 Nous recommandons la première forme pour des questions de performances et de maintenance.  
  
 `setlocale( LC_ALL, ".<code_page>" );`  
 Définit la page de codes en fonction de la valeur indiquée par *<code_page>*, ainsi que du pays/région et de la langue par défaut (tels que définis par le système d’exploitation hôte) pour la page de codes spécifiée.  
  
 La catégorie doit être `LC_ALL` ou `LC_CTYPE` pour effectuer un changement de page de codes. Par exemple, si le pays/la région et la langue par défaut du système d'exploitation hôte sont « États-Unis » et « anglais », les deux appels suivants à `setlocale` sont fonctionnellement équivalents :  
  
 `setlocale( LC_ALL, ".1252" );`  
  
 `setlocale( LC_ALL, "English_United States.1252");`  
  
 Pour plus d’informations, consultez la directive pragma [setlocale](../../preprocessor/setlocale.md) dans [Référence du préprocesseur C/C++](../../preprocessor/c-cpp-preprocessor-reference.md).  
  
 La fonction [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) est utilisée pour déterminer si `setlocale` affecte les paramètres régionaux de tous les threads d’un programme ou uniquement les paramètres régionaux du thread appelant.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`setlocale`|\<locale.h>|  
|`_wsetlocale`|\<locale.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_setlocale.c  
//   
// This program demonstrates the use of setlocale when  
// using two independent threads.  
//  
  
#include <locale.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date in the current  
// locale's format.  
int get_date(unsigned char* str)  
{  
    __time64_t ltime;  
    struct tm  thetime;  
  
    // Retrieve the current time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // "%#x" is the long date representation in the  
    // current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm *)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to the argument  
// and prints the date.  
uintptr_t __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
    char * locale = (char *)pArguments;  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, locale));  
  
    // Retrieve the date string from the helper function  
    if (get_date(str) == 0)  
    {  
        printf("The date in %s locale is: '%s'\n", locale, str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread sets the locale to English   
// and then spawns a second thread (above) and prints the date.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Set the locale of the main thread to US English.  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "en-US"));  
  
    // Create the second thread with a German locale.  
    // Our thread function takes an argument of the locale to use.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      "de-DE", 0, &threadID );  
  
    if (get_date(str) == 0)  
    {  
        // Retrieve the date string from the helper function  
        printf("The date in en-US locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
```Output  
The thread locale is now set to en-US.  
The time in en-US locale is: 'Wednesday, May 12, 2004'  
  
The thread locale is now set to de-DE.  
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Chaînes relatives aux noms, aux langues, au pays et à la région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)