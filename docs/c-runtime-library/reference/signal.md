---
title: "signal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "signal"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "signal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "signal (fonction)"
ms.assetid: 094118de-d789-4063-b4f4-cffcc80bf29d
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# signal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Paramètre la gestion du signal d'interruption.  
  
> [!IMPORTANT]
>  N'utilisez pas cette méthode pour arrêter une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], sauf dans les scénarios de test ou de débogage.  Les méthodes de programmation ou de l'interface utilisateur pour fermer une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ne sont pas autorisées d'après la section 3.6 des [Critères de certification pour les applications Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889).  Pour plus d'informations, consultez [Cycle de vie d'une application \(applications du Windows Store\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Syntaxe  
  
```  
void (__cdecl *signal(  
   int sig,   
   void (__cdecl *func ) (int [, int ] )))   
   (int);  
```  
  
#### Paramètres  
 `sig`  
 Valeur du signal.  
  
 `func`  
 Fonction à exécuter.  Le premier paramètre est une valeur de signal et le deuxième paramètre est un sous\-code qui peut être utilisé lorsque le premier paramètre est SIGFPE.  
  
## Valeur de retour  
 `signal` retourne la valeur précédente de `func` qui est associée au signal donné.  Par exemple, si la valeur précédente de `func` était `SIG_IGN`, la valeur de retour est également `SIG_IGN`.  Une valeur de retour égale à `SIG_ERR` indique une erreur; dans ce cas, `errno` est fixé à `EINVAL`.  
  
 Pour plus d'informations sur les codes de retour, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `signal` permet à un processus de choisir une manière parmi plusieures pour gérer un signal d'interruption du système d'exploitation.  L'argument `sig` est l'interruption à laquelle `signal` répond ; il doit être l'une des constantes du manifestes suivantes, définies dans SIGNAL.H.  
  
|Valeur de `sig`|Description|  
|---------------------|-----------------|  
|`SIGABRT`|Abnormal\_termination|  
|`SIGFPE`|Erreur de virgule flottante|  
|`SIGILL`|Instruction non conforme|  
|`SIGINT`|Signal CTRL\+C|  
|`SIGSEGV`|Accès non conforme au stockage|  
|`SIGTERM`|Demande d'arrêt|  
  
 Si `sig` ne fait pas partie des valeurs ci\-dessus, le gestionnaire de paramètres non valides est appelé, comme défini dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `SIG_ERR`.  
  
 Par défaut, `signal` termine le programme appelant par le code de sortie 3, indépendamment de la valeur de `sig`.  
  
> [!NOTE]
>  `SIGINT` n'est pris en charge pour aucune application Win32.  Lorsqu'une interruption CTRL\+C se produit, les systèmes d'exploitation Win32 génèrent un nouveau thread pour gérer spécifiquement cette interruption.  Cela peut amener une application à un seul thread, telle que celle dans UNIX, à devenir multithread et à provoquer un comportement inattendu.  
  
 L'argument `func` est une adresse d'un gestionnaire de signal que vous écrivez, ou l'adresse d'une des constantes prédéfinies `SIG_DFL` ou `SIG_IGN`, qui sont également définies dans SIGNAL.H.  Si `func` est une fonction, elle est installée en tant que gestionnaire de signal pour le signal donné.  Le prototype du gestionnaire de signal requiert un argument formel, `sig`, de type `int`.  Le système d'exploitation fournit l'argument réel via `sig` lorsqu'une interruption se produit ; l'argument est le signal qui a généré l'interruption.  Par conséquent, vous pouvez utiliser les six constantes du manifeste \(répertoriées dans le tableau précédent\) dans votre gestionnaire de signal pour déterminer quelle interruption se produit puis prendre des mesures en conséquence.  Par exemple, vous pouvez appeler `signal` deux fois pour assigner le même gestionnaire à deux signaux différents, puis tester l'argument `sig` dans le gestionnaire pour prendre des mesures différentes selon le signal reçu.  
  
 Si vous êtes à la recherche d'exceptions de virgule flottante \(`SIGFPE`\), `func` indique une fonction qui prend un deuxième argument facultatif qui est l'une des nombreuses constantes du manifeste—définies dans FLOAT.H— sous la forme `FPE_xxx`.  Lorsqu'un signal `SIGFPE` se produit, vous pouvez tester la valeur du deuxième argument pour déterminer le type d'exception de virgule flottante puis agir en conséquence.  Cet argument et ses valeurs possibles sont des extensions Microsoft.  
  
 Pour les exceptions de virgule flottante, la valeur de `func` n'est pas réinitialisée lorsque le signal est reçu.  Pour récupérer d'exceptions de virgule flottante, utilisez les clauses try\/except pour cerner les opérations de virgule flottante.  Il est également possible de récupérer à l'aide de [setjmp](../../c-runtime-library/reference/setjmp.md) avec [longjmp](../../c-runtime-library/reference/longjmp.md).  Dans les deux cas, les processus d'appel reprennent l'exécution et quitte l'état de virgule flottante du processus indéfini.  
  
 Si le gestionnaire de signature réapparait, le processus d'appel reprend l'exécution immédiatement après le moment auquel il a reçu le signal d'interruption.  Cela est vrai quel que soit le type de signal ou de mode d'opération.  
  
 Avant que la fonction spécifiée soit exécutée, la valeur de `func` est paramétrée à `SIG_DFL`.  Le signal suivant d'interruption est traité comme décrit pour `SIG_DFL`, sauf un appel d'intervention à `signal` précise le contraire.  Vous pouvez utiliser cette fonctionnalité afin de réinitialiser des signaux dans la fonction appelée.  
  
 Dans la mesure où les routines du gestionnaire de signal sont généralement appelées de façon asynchrone, lorsqu'une interruption se produit, votre fonction de gestion de signal peut obtenir la main lorsqu'une opération du runtime est incomplète et dans un état inconnu.  La liste suivante résume les restrictions qui déterminent les fonctions que vous pouvez utiliser dans votre routine de gestion de signal.  
  
-   Ne publiez pas les routines de bas niveau ou d'E\/S de STDIO.H \(par exemple, `printf` ou `fread`\).  
  
-   N'appelez pas les routines du segment de mémoire ou toute routine qui utilise les routines du segment de mémoire \(par exemple, `malloc`, `_strdup`, ou `_putenv`\).  Consultez [malloc](../../c-runtime-library/reference/malloc.md) pour plus d'informations.  
  
-   N'utilisez aucune fonction qui génère un appel au système \(par exemple, `_getcwd` ou `time`\).  
  
-   N'utilisez pas `longjmp` à moins que l'interruption ne soit provoquée par une exception de virgule flottante \(autrement dit, si `sig` est `SIGFPE`\).  Dans ce cas, réinitialisez d'abord le package de virgule flottante en utilisant un appel à `_fpreset`.  
  
-   N'utilisez pas routine de superposition.  
  
 Un programme doit contenir du code à virgule flottante s'il a pour but d'intercepter l'exception `SIGFPE` en utilisant la fonction.  Si votre programme n'a pas de code à virgule flottante et qu'il requiert le code du gestionnaire de signal de la bibliothèque runtime, déclarez juste un chiffre de type double volatile et initialisez le à zéro :  
  
```  
volatile double d = 0.0f;   
```  
  
 Les signaux `SIGILL` et `SIGTERM` ne sont pas générés sous Windows.  Ils sont inclus pour la compatibilité ANSI.  Par conséquent, vous pouvez définir des gestionnaires de signal pour ces signaux à l'aide de `signal`, et vous pouvez également générer explicitement ces signaux en appelant [raise](../../c-runtime-library/reference/raise.md).  
  
 Les paramètres de signal ne sont pas conservés dans les processus engendrés qui sont créés par les appels aux fonctions `_exec` ou `_spawn`.  Les paramètres du signal sont réinitialisés à la valeur par défaut dans le nouveau processus.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`signal`|\<signal.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser `signal` pour ajouter un comportement personnalisé au signal `SIGABRT`.  Pour plus d'informations sur le comportement d'arrêt, consultez [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md).  
  
```cpp  
// crt_signal.c  
// compile with: /EHsc /W4  
// Use signal to attach a signal handler to the abort routine  
#include <stdlib.h>  
#include <signal.h>  
#include <tchar.h>  
  
void SignalHandler(int signal)  
{  
    if (signal == SIGABRT) {  
        // abort signal handler code  
    } else {  
        // ...  
    }  
}  
  
int main()  
{  
    typedef void (*SignalHandlerPointer)(int);  
  
    SignalHandlerPointer previousHandler;  
    previousHandler = signal(SIGABRT, SignalHandler);  
  
    abort();  
}  
  
```  
  
  **Cette application avait demandé le runtime afin de terminer son exécution de manière inhabituelle.**  
**Veuillez contacter l'équipe du support technique de l'application pour plus d'informations.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_fpreset](../../c-runtime-library/reference/fpreset.md)   
 [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)