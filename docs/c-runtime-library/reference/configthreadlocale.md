---
title: "_configthreadlocale | Microsoft Docs"
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
  - "_configthreadlocale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_configthreadlocale"
  - "configthreadlocale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_configthreadlocale (fonction)"
  - "configthreadlocale (fonction)"
  - "paramètres régionaux, par thread"
  - "paramètres régionaux par thread"
  - "paramètres régionaux du thread"
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _configthreadlocale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Configure les options de paramètres régionaux au sein d'un thread.  
  
## Syntaxe  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
#### Paramètres  
 `type`  
 Option à définir.  L'une des étapes répertoriées dans le tableau suivant.  
  
## Valeur de retour  
 L'état précédent de paramètres régionaux au sein du thread \(`_DISABLE_PER_THREAD_LOCALE` ou `_ENABLE_PER_THREAD_LOCALE`\), ou \-1 en cas de défaillance.  
  
## Notes  
 La fonction `_configurethreadlocale` est utilisée pour contrôler l'utilisation des paramètres régionaux spécifiques des threads.  Utilisez une de ces options de spécifier ou déterminer l'état par thread de paramètres régionaux :  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 Faire utiliser des paramètres régionaux spécifiques au thread actuel.  Les appels suivants à `setlocale` dans ce thread affectent uniquement les propres paramètres régionaux du thread.  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 Faire utiliser au thread actuel les paramètres régionaux globaux.  Les appels suivants à `setlocale` dans ce thread affectent les autres threads utilisant les paramètres régionaux globaux.  
  
 `0`  
 Récupère le paramètre actuel pour ce thread particulier.  
  
 Ces fonctions affectent le comportement de `setlocale`, en`_tsetlocale`, `_wsetlocale`, `_beginthread`, et `_beginthreadex`.  Si une autre méthode est utilisée pour créer des threads, les paramètres régionaux n'ont aucun effet sur ces threads.  
  
 Lorsque les paramètres régionaux par thread sont désactivés, tout appel suivant à `setlocale` ou `_wsetlocale` modifie les paramètres régionaux de tous les threads.  Lorsque les paramètres régionaux par thread sont activés, `setlocale` ou `_wsetlocale` affectent seulement les paramètres régionaux du thread actuel.  
  
 Si vous utilisez `_configurethreadlocale` pour activer les paramètres régionaux par thread, nous vous recommandons d'appeler `setlocale` ou `_wsetlocale` pour définir les paramètres régionaux par défaut dans ce thread immédiatement après.  
  
 Si `type` ne fait pas partie des valeurs répertoriées dans la table, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction définit `errno` à `EINVAL` et retourne \-1.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_configthreadlocale`|\<locale.h\>|  
  
## Exemple  
  
```  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using is two independent threads.  
//  
  
#include <locale.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date and time in the current  
// locale's format.  
int get_time(unsigned char* str)  
{  
    __time64_t  ltime;  
    struct tm   thetime;  
  
    // Retieve the time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // using %#x is the long date representation,  
    // appropriate to the current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm*)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to German  
// and prints the time.  
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
  
    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI)  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "German"));  
  
    // Retrieve the time string from the helper function  
    if (get_time(str) == 0)  
    {  
        printf("The time in German locale is: '%s'\n", str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread spawns a second thread (above) and then  
// sets the locale to English and prints the time.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Retrieve the time string from the helper function  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "English"));  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      NULL, 0, &threadID );  
  
    if (get_time(str) == 0)  
    {  
        // Retrieve the time string from the helper function  
        printf("The time in English locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
  **Les paramètres régionaux du thread sont désormais à la valeur English\_United States.1252.**  
**L'heure dans les paramètres régionaux anglais est : « Wednesday, May 12, 2004 »**  
**Les paramètres régionaux du thread sont désormais à la valeur German\_Germany.1252.**  
**L'heure dans les paramètres régionaux allemands est : 'Mittwoch, 12.  Mai 2004 '**    
## Équivalent .NET Framework  
 Non applicable. Toutefois, consultez [Utilisation de la propriété CurrentCulture](http://msdn.microsoft.com/fr-fr/3156042d-6082-4205-90b4-c917ae6a3ba6).  
  
## Voir aussi  
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_beginthread, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Multithreading et paramètres régionaux](../../parallel/multithreading-and-locales.md)