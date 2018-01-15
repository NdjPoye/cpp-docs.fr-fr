---
title: abort | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: abort
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
f1_keywords: Abort
dev_langs: C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6577ca7927d42e12aa62ed100b9572b7270208f
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/05/2018
---
# <a name="abort"></a>abort

Interrompt le processus actuel et retourne un code d’erreur.

> [!NOTE]
> N’utilisez pas cette méthode pour arrêter une application Microsoft Store ou [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] application, sauf dans les scénarios de débogage ou de test. Méthodes de programmation ou l’interface utilisateur pour fermer une application de magasin ne sont pas autorisées en fonction de la [des stratégies Microsoft Store](/legal/windows/agreements/store-policies). Pour plus d’informations, consultez [cycle de vie des applications UWP](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Syntaxe

```c
void abort( void );
```

## <a name="return-value"></a>Valeur de retour

`abort` ne retourne pas le contrôle au processus appelant. Par défaut, elle recherche un gestionnaire de signal d’abandon et déclenche `SIGABRT` si tel gestionnaire est défini. Ensuite, `abort` termine le processus actuel et retourne un code de sortie au processus parent.

## <a name="remarks"></a>Notes

**Section spécifique à Microsoft**

Par défaut, quand une application est générée avec la bibliothèque runtime de débogage, la routine `abort` affiche un message d’erreur avant que `SIGABRT` ne soit déclenché. Pour les applications de console en cours d’exécution en mode console, le message est envoyé à `STDERR`. Les applications de bureau Windows et les applications de console qui s’exécutent en mode fenêtré affichent le message dans une boîte de message. Pour supprimer le message, utilisez [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md) pour effacer l’indicateur `_WRITE_ABORT_MSG`. Le message affiché dépend de la version de l’environnement d’exécution utilisé. Pour les applications générées à l’aide des versions les plus récentes de Visual C++, le message ressemble à ceci :

> R6010 - abort() a été appelée.

Dans les versions précédentes de la bibliothèque runtime C, le message suivant était affiché :

> This application has requested the Runtime to terminate it in an unusual way. Please contact the application’s support team for more information.

Quand le programme est compilé en mode débogage, la boîte de message affiche les options **Abandonner**, **Réessayer** ou **Ignorer**. Si l’utilisateur choisit **Abandonner**, le programme se termine immédiatement et retourne le code de sortie 3. Si l’utilisateur choisit **Réessayer**, un débogueur est appelé pour le débogage juste-à-temps, si disponible. Si l’utilisateur choisit **Ignorer**, `abort` continue le traitement normal.

Dans les versions de détail et de débogage, `abort` vérifie ensuite si un gestionnaire de signal d’abandon est défini. Si un gestionnaire de signal personnalisé est défini, `abort` appelle `raise(SIGABRT)`. Utilisez la fonction [signal](../../c-runtime-library/reference/signal.md) pour associer une fonction de gestionnaire de signal d’abandon au signal `SIGABRT`. Vous pouvez effectuer des actions personnalisées, telles que nettoyer les ressources ou enregistrer des informations, et arrêter l’application avec votre propre code d’erreur dans la fonction de gestionnaire. Si aucun gestionnaire de signal personnalisé n’est défini, `abort` ne déclenche pas le signal `SIGABRT`.

Par défaut, dans les versions non debug des applications de bureau ou de la console, `abort` appelle ensuite le mécanisme de Service de création de rapports d’erreurs Windows (autrefois appelé récupération d’urgence. Watson) pour signaler les échecs à Microsoft. Vous pouvez activer ou désactiver ce comportement en appelant `_set_abort_behavior` et en définissant ou masquant l’indicateur `_CALL_REPORTFAULT`. Quand l’indicateur est défini, Windows affiche une boîte de message dont le texte ressemble à ceci : « Le programme a cessé de fonctionner correctement à cause d’un problème. » L’utilisateur peut choisir d’appeler un débogueur avec un bouton **Déboguer**, ou choisir le bouton **Fermer le programme** pour mettre fin à l’application avec un code d’erreur défini par le système d’exploitation.

Si le gestionnaire de rapport d’erreurs Windows n’est pas appelé, `abort` appelle [_exit](../../c-runtime-library/reference/exit-exit-exit.md) pour terminer le processus avec le code de sortie 3 et retourne le contrôle au processus parent ou au système d’exploitation. `_exit` ne vide pas les mémoires tampons de flux ou n’effectue pas de traitement `atexit`/`_onexit`.

Pour plus d’informations sur le débogage CRT, consultez [Techniques de débogage CRT](/visualstudio/debugger/crt-debugging-techniques).

**Fin de la section spécifique à Microsoft**

## <a name="requirements"></a>Configuration requise

|Routine|En-tête requis|
|-------------|---------------------|
|`abort`|\<process.h> ou \<stdlib.h>|

## <a name="example"></a>Exemple

Le programme suivant essaie d’ouvrir un fichier et s’interrompt si la tentative échoue.

```C
// crt_abort.c
// compile with: /TC
// This program demonstrates the use of
// the abort function by attempting to open a file
// and aborts if the attempt fails.

#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    FILE    *stream = NULL;
    errno_t err = 0;

    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );
    if ((err != 0) || (stream == NULL))
    {
        perror( "File could not be opened" );
        abort();
    }
    else
    {
        fclose( stream );
    }
}
```

```Output
File could not be opened: No such file or directory
```

## <a name="see-also"></a>Voir aussi

[Utilisation d’abort](../../cpp/using-abort.md)  
[abort, fonction](../../c-language/abort-function-c.md)  
[Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)  
[_exec, _wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)  
[exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[raise](../../c-runtime-library/reference/raise.md)  
[signal](../../c-runtime-library/reference/signal.md)  
[_spawn, _wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)  
[_DEBUG](../../c-runtime-library/debug.md)  
[_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)  
