---
title: signal | Microsoft Docs
ms.custom: 
ms.date: 02/12/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- signal
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- signal
dev_langs:
- C++
helpviewer_keywords:
- signal function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23eae404bf5f8e2227d68189938defb2308f5e6b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="signal"></a>signal

Définit la gestion du signal d'interruption.

> [!IMPORTANT]
> N’utilisez pas cette méthode pour arrêter une application Microsoft Store, à l’exception de test ou de scénarios de débogage. Méthodes de programmation ou l’interface utilisateur pour fermer une application de magasin ne sont pas autorisées en fonction de la [des stratégies Microsoft Store](http://go.microsoft.com/fwlink/?LinkId=865936). Pour plus d’informations, consultez [cycle de vie des applications UWP](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Syntaxe

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>Paramètres
_sig_  
Valeur du signal.

_func_  
Le deuxième paramètre est un pointeur vers la fonction à exécuter. Le premier paramètre est une valeur de signal et le deuxième paramètre est un sous-code qui peut être utilisé lorsque le premier paramètre est SIGFPE.

## <a name="return-value"></a>Valeur de retour

`signal` Retourne la valeur précédente de func associé au signal donné. Par exemple, si la valeur précédente de _func_ a été `SIG_IGN`, la valeur de retour est également `SIG_IGN`. La valeur de retour `SIG_ERR` indique une erreur ; dans ce cas, `errno` a la valeur `EINVAL`.

Pour plus d’informations sur les codes de retour, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Notes

La fonction `signal` permet à un processus de choisir une des différentes méthodes pour gérer un signal d'interruption à partir du système d'exploitation. Le _sig_ argument est l’interruption à laquelle `signal` répond ; il doit être une des constantes de manifeste suivantes, qui sont définies dans un SIGNAL. H.

|_SIG_ valeur|Description|
|-----------------|-----------------|
|`SIGABRT`|Arrêt anormal|
|`SIGFPE`|Erreur de virgule flottante|
|`SIGILL`|Instruction non conforme|
|`SIGINT`|Signal CTRL+C|
|`SIGSEGV`|Accès au stockage non conforme|
|`SIGTERM`|Demande d'arrêt|

Si _sig_ n’est pas une des valeurs ci-dessus, le Gestionnaire de paramètre non valide est appelé, comme défini dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) . Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `SIG_ERR`.

Par défaut, `signal` termine le programme appelant avec code de sortie 3, quelle que soit la valeur de _sig_.

> [!NOTE]
> `SIGINT` n'est pris en charge pour aucune application Win32. Lorsqu'une interruption CTRL+C se produit, les systèmes d'exploitation Win32 génèrent un nouveau thread pour gérer spécifiquement cette interruption. Cela peut amener une application à un seul thread, par exemple celle dans UNIX, à devenir multithread et à provoquer un comportement inattendu.

Le _func_ argument est une adresse d’un gestionnaire de signal que vous écrivez, ou à une des constantes prédéfinies `SIG_DFL` ou `SIG_IGN`, qui sont également définies dans un SIGNAL. H. Si _func_ est une fonction, il est installé en tant que gestionnaire de signal pour le signal donné. Prototype du Gestionnaire de signal requiert un argument formel, _sig_, de type `int`. Le système d’exploitation fournit l’argument réel via _sig_ lorsqu’une interruption se produit ; l’argument est le signal qui a généré l’interruption. Par conséquent, vous pouvez utiliser les six constantes de manifeste (répertoriées dans le tableau précédent) de votre gestionnaire de signal pour déterminer le type d'interruption et prendre les mesures appropriées. Par exemple, vous pouvez appeler `signal` à deux reprises pour assigner le même gestionnaire à deux signaux différents, puis tester la _sig_ argument dans le gestionnaire pour prendre des mesures différentes selon le signal reçu.

Si vous testez des exceptions de virgule flottante (`SIGFPE`), _func_ pointe vers une fonction qui accepte un deuxième argument facultatif qui est une des nombreuses constantes de manifeste, défini dans le type FLOAT. H, sous la forme `FPE_xxx`. Lorsqu'un signal `SIGFPE` se produit, vous pouvez tester la valeur du deuxième argument pour déterminer le type d'exception à virgule flottante et agir en conséquence. Cet argument et ses valeurs possibles sont des extensions Microsoft.

Pour les exceptions à virgule flottante, la valeur de _func_ n’est pas réinitialisée lorsque le signal est reçu. Pour récupérer des exceptions à virgule flottante, utilisez les clauses try/except pour cerner les opérations à virgule flottante. Il est aussi possible d’effectuer une récupération en utilisant [setjmp](../../c-runtime-library/reference/setjmp.md) avec [longjmp](../../c-runtime-library/reference/longjmp.md). Dans les deux cas, le processus appelant reprend l'exécution et quitte l'état à virgule flottante du processus non défini.

Si le gestionnaire de signal retourne, le processus appelant reprend l'exécution immédiatement après le moment où il a reçu le signal d'interruption. Cela est vrai quel que soit le type de signal ou le mode de fonctionnement.

Avant l’exécution de la fonction spécifiée, la valeur de _func_ a la valeur `SIG_DFL`. Le signal d'interruption suivant est traité comme décrit pour `SIG_DFL`, sauf si un appel d'intervention à `signal` précise le contraire. Vous pouvez utiliser cette fonctionnalité pour réinitialiser les signaux dans la fonction appelée.

Dans la mesure où les routines de gestion de signal sont généralement appelées de façon asynchrone lorsqu'une interruption se produit, votre fonction de gestion de signal peut obtenir le contrôle lorsqu'une opération du runtime est incomplète et dans un état inconnu. La liste suivante résume les restrictions qui déterminent les fonctions que vous pouvez utiliser dans votre routine de gestion de signal.

- Ne publiez pas les routines d'E/S STDIO.H ou de niveau inférieur (par exemple, `printf` ou `fread`).

- N'appelez pas les routines de tas ou toute routine qui utilise les routines de tas (par exemple, `malloc`, `_strdup` ou `_putenv`). Pour plus d’informations, consultez [malloc](../../c-runtime-library/reference/malloc.md).

- N'utilisez aucune fonction qui génère un appel du système (par exemple, `_getcwd` ou `time`).

- N’utilisez pas `longjmp` à moins que l’interruption soit provoquée par une exception à virgule flottante (autrement dit, _sig_ est `SIGFPE`). Dans ce cas, réinitialisez d'abord le package à virgule flottante à l'aide d'un appel à `_fpreset`.

- N'utilisez aucune routine de superposition.

Un programme doit contenir un code à virgule flottante s'il doit intercepter l'exception `SIGFPE` à l'aide de la fonction. Si votre programme ne contient pas de code à virgule flottante et qu'il requiert le code de gestion de signal de la bibliothèque runtime, déclarez un chiffre de type double volatile et initialisez-le à zéro :

`volatile double d = 0.0f;`

Les signaux `SIGILL` et `SIGTERM` ne sont pas générés sous Windows. Ils sont inclus pour la compatibilité ANSI. Par conséquent, vous pouvez définir des gestionnaires de signal pour ces signaux à l’aide de `signal`, et vous pouvez aussi générer explicitement ces signaux en appelant [raise](../../c-runtime-library/reference/raise.md).

Les paramètres de signal ne sont pas conservés dans les processus engendrés qui sont créés par les appels aux fonctions `_exec` ou `_spawn`. Les valeurs par défaut des paramètres de signal sont réinitialisées dans le nouveau processus.

## <a name="requirements"></a>Configuration requise

|Routine|En-tête requis|
|-------------|---------------------|
|`signal`|\<signal.h >|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

L'exemple suivant montre comment utiliser `signal` pour ajouter un comportement personnalisé au signal `SIGABRT`. Pour plus d’informations sur le comportement d’arrêt, consultez [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md).

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Voir aussi

[Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[_exec, _wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)  
[exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[_fpreset](../../c-runtime-library/reference/fpreset.md)  
[_spawn, _wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)  
