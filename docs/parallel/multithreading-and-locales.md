---
title: "Multithreading et param&#232;tres r&#233;gionaux | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "paramètres régionaux (C++), multithreading"
  - "multithreading (C++), paramètres régionaux"
  - "paramètres régionaux par thread"
  - "threads (C++), paramètres régionaux"
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading et param&#232;tres r&#233;gionaux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque Runtime C et la bibliothèque C\+\+ standard prennent toutes deux en charge la modification des paramètres régionaux de votre programme.  Cette rubrique traite des problèmes qui surviennent en utilisant les fonctionnalités de paramètres régionaux des deux bibliothèques dans une application multithread.  
  
## Notes  
 Avec la bibliothèque Runtime C, vous pouvez créer des applications multithread à l'aide des fonctions `_beginthread` et `_beginthreadex`.  Cette rubrique ne couvre que les applications multithread créées à l'aide de ces fonctions.  Pour plus d'informations, consultez [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
 Pour modifier les paramètres régionaux à l'aide de la bibliothèque Runtime C, utilisez la fonction [setlocale](../preprocessor/setlocale.md).  Dans les versions précédentes de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], cette fonction modifiait toujours les paramètres régionaux dans l'application entière.  Désormais il est possible de définir les paramètres régionaux par thread.  Cette opération est réalisée à l'aide de la fonction [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md).  Pour spécifier que [setlocale](../preprocessor/setlocale.md) ne doit modifier les paramètres régionaux que dans le thread actuel, appelez `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` dans ce thread.  Inversement, l'appel à `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` impliquera l'utilisation par le thread des paramètres régionaux globaux, et tout appel à [setlocale](../preprocessor/setlocale.md) dans ce thread modifiera les paramètres régionaux dans tous les threads qui n'auront pas explicitement activé de paramètres régionaux par thread.  
  
 Pour modifier les paramètres régionaux à l'aide de la bibliothèque Runtime C\+\+, utilisez la [locale, classe](../standard-library/locale-class.md).  En appelant la méthode [locale::global](../Topic/locale::global.md), vous modifiez les paramètres régionaux dans chaque thread qui n'a pas explicitement activé de paramètres régionaux par thread.  Pour modifier les paramètres régionaux dans un thread seul ou dans une partie d'une application, créez simplement une instance d'un objet `locale` dans ce thread ou cette partie de code.  
  
> [!NOTE]
>  L'appel à [locale::global](../Topic/locale::global.md) modifie les paramètres régionaux à la fois pour la bibliothèque C\+\+ standard et pour la bibliothèque Runtime C.  Toutefois, l'appel à [setlocale](../preprocessor/setlocale.md) modifie uniquement les paramètres régionaux pour la bibliothèque Runtime C ; la bibliothèque C\+\+ standard n'est pas affectée.  
  
 Les exemples suivants indiquent comment utiliser la fonction [setlocale](../preprocessor/setlocale.md), la [locale, classe](../standard-library/locale-class.md) et la fonction [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) pour modifier les paramètres régionaux d'une application selon différents scénarios.  
  
## Exemple  
 Dans cet exemple, le thread principal génère deux threads enfants.  Le premier thread, Thread A, active les paramètres régionaux par thread en appelant `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Le deuxième thread, Thread B, de même que le thread principal, n'activent pas les paramètres régionaux par thread.  Thread A entreprend alors de modifier les paramètres régionaux à l'aide de la fonction [setlocale](../preprocessor/setlocale.md) de la bibliothèque Runtime C.  
  
 Comme Thread A a activé les paramètres régionaux par thread, seules les fonctions de la bibliothèque Runtime C dans Thread A commencent à utiliser les paramètres régionaux « français ».  Les fonctions de la bibliothèque Runtime C dans Thread B et dans le thread principal continuent à utiliser les paramètres régionaux « C ».  De même, comme [setlocale](../preprocessor/setlocale.md) n'affecte pas les paramètres régionaux de la bibliothèque C\+\+ standard, tous les objets de la bibliothèque C\+\+ standard continuent d'utiliser les paramètres régionaux « C ».  
  
```  
// multithread_locale_1.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread A\] Les paramètres régionaux par thread sont activés.**  
**\[Thread A\] Paramètres régionaux CRT définis sur "French\_France.1252"**  
**\[Thread A\] locale::global définis sur "C"**  
**\[Thread B\] Les paramètres régionaux par thread NE SONT PAS activés.**  
**\[Thread B\] Paramètres régionaux CRT définis sur "C"**  
**\[Thread B\] locale::global définis sur "C"**  
**\[Thread principal\] Les paramètres régionaux par thread ne sont pas activés.**  
**\[Thread principal\] Paramètres régionaux CRT définis sur "C"**  
**\[Thread principal\] locale::global définis sur "C"**   
## Exemple  
 Dans cet exemple, le thread principal génère deux threads enfants.  Le premier thread, Thread A, active les paramètres régionaux par thread en appelant `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Le deuxième thread, Thread B, de même que le thread principal, n'activent pas les paramètres régionaux par thread.  Thread A entreprend alors modifier les paramètres régionaux à l'aide de la méthode [locale::global](../Topic/locale::global.md) de la bibliothèque C\+\+ standard.  
  
 Comme Thread A a activé les paramètres régionaux par thread, seules les fonctions de la bibliothèque Runtime C dans Thread A commencent à utiliser les paramètres régionaux « français ».  Les fonctions de la bibliothèque Runtime C dans Thread B et dans le thread principal continuent à utiliser les paramètres régionaux « C ».  Toutefois, comme la méthode [locale::global](../Topic/locale::global.md) modifie les paramètres régionaux « globalement », tous les objets de la bibliothèque C\+\+ standard dans tous les threads commencent à utiliser les paramètres régionaux « français ».  
  
```  
// multithread_locale_2.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread A\] Les paramètres régionaux par thread sont activés.**  
**\[Thread A\] Paramètres régionaux CRT définis sur "French\_France.1252"**  
**\[Thread A\] locale::global définis sur "French\_France.1252"**  
**\[Thread B\] Les paramètres régionaux par thread NE SONT PAS activés.**  
**\[Thread B\] Paramètres régionaux CRT définis sur "C"**  
**\[Thread B\] locale::global définis sur "French\_France.1252"**  
**\[Thread principal\] Les paramètres régionaux par thread ne sont pas activés.**  
**\[Thread principal\] Paramètres régionaux CRT définis sur "C"**  
**\[Thread principal\] locale::global définis sur "French\_France.1252"**   
## Exemple  
 Dans cet exemple, le thread principal génère deux threads enfants.  Le premier thread, Thread A, active les paramètres régionaux par thread en appelant `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Le deuxième thread, Thread B, de même que le thread principal, n'activent pas les paramètres régionaux par thread.  Thread B entreprend alors de modifier les paramètres régionaux à l'aide de la fonction [setlocale](../preprocessor/setlocale.md) de la bibliothèque Runtime C.  
  
 Comme Thread B n'a pas activé les paramètres régionaux par thread, les fonctions de la bibliothèque Runtime C dans Thread B et dans le thread principal commencent à utiliser les paramètres régionaux « français ».  Les fonctions de la bibliothèque Runtime C dans Thread A continuent à utiliser les paramètres régionaux « C », car Thread A a activé les paramètres régionaux par thread.  De même, comme [setlocale](../preprocessor/setlocale.md) n'affecte pas les paramètres régionaux de la bibliothèque C\+\+ standard, tous les objets de la bibliothèque C\+\+ standard continuent d'utiliser les paramètres régionaux « C ».  
  
```  
// multithread_locale_3.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread B\] Les paramètres régionaux par thread NE SONT PAS activés.**  
**\[Thread B\] Paramètres régionaux CRT définis sur "French\_France.1252"**  
**\[Thread B\] locale::global définis sur "C"**  
**\[Thread A\] Les paramètres régionaux par thread sont activés.**  
**\[Thread A\] Paramètres régionaux CRT définis sur "C"**  
**\[Thread A\] locale::global définis sur "C"**  
**\[Thread principal\] Les paramètres régionaux par thread ne sont pas activés.**  
**\[Thread principal\] Paramètres régionaux CRT définis sur "French\_France.1252"**  
**\[Thread principal\] locale::global définis sur "C"**   
## Exemple  
 Dans cet exemple, le thread principal génère deux threads enfants.  Le premier thread, Thread A, active les paramètres régionaux par thread en appelant `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`.  Le deuxième thread, Thread B, de même que le thread principal, n'activent pas les paramètres régionaux par thread.  Thread B entreprend alors de modifier les paramètres régionaux à l'aide de la méthode [locale::global](../Topic/locale::global.md) de la bibliothèque C\+\+ standard.  
  
 Comme Thread B n'a pas activé les paramètres régionaux par thread, les fonctions de la bibliothèque Runtime C dans Thread B et dans le thread principal commencent à utiliser les paramètres régionaux « français ».  Les fonctions de la bibliothèque Runtime C dans Thread A continuent à utiliser les paramètres régionaux « C », car Thread A a activé les paramètres régionaux par thread.  Toutefois, comme la méthode [locale::global](../Topic/locale::global.md) modifie les paramètres régionaux « globalement », tous les objets de la bibliothèque C\+\+ standard dans tous les threads commencent à utiliser les paramètres régionaux « français ».  
  
```  
// multithread_locale_4.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[Thread B\] Les paramètres régionaux par thread NE SONT PAS activés.**  
**\[Thread B\] Paramètres régionaux CRT définis sur "French\_France.1252"**  
**\[Thread B\] locale::global définis sur "French\_France.1252"**  
**\[Thread A\] Les paramètres régionaux par thread sont activés.**  
**\[Thread A\] Paramètres régionaux CRT définis sur "C"**  
**\[Thread A\] locale::global définis sur "French\_France.1252"**  
**\[Thread principal\] Les paramètres régionaux par thread ne sont pas activés.**  
**\[Thread principal\] Paramètres régionaux CRT définis sur "French\_France.1252"**  
**\[Thread principal\] locale::global définis sur "French\_France.1252"**   
## Voir aussi  
 [Prise en charge du multithreading pour le code plus ancien \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Paramètres régionaux](../c-runtime-library/locale.md)   
 [\<clocale\>](../standard-library/clocale.md)   
 [\<locale\>](../standard-library/locale.md)   
 [locale, classe](../standard-library/locale-class.md)