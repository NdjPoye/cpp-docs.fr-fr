---
title: "Contrôle de processus et d’environnement │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d5198dcef7d24d2755c21b90802b19e809c5b8da
ms.lasthandoff: 02/24/2017

---
# <a name="process-and-environment-control"></a>Contrôle de processus et d'environnement
Utilisez les routines de contrôle de processus pour démarrer, arrêter et gérer les processus à partir d’un programme. Utilisez les routines de contrôle de l’environnement pour obtenir et modifier les informations sur l’environnement de système d’exploitation.  
  
### <a name="process-and-environment-control-functions"></a>Fonctions de contrôle de processus et d’environnement  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|---------|-------------------------------|  
|[abort](../c-runtime-library/reference/abort.md)|Abandonner le processus sans vider les mémoires tampons ou appeler des fonctions enregistrées par `atexit` et `_onexit`|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Vérifier une erreur logique|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), macros|Similaire à `assert`, mais uniquement disponible dans les versions Debug des bibliothèques Runtime|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|Planifier des routines à exécuter à l’arrêt du programme|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Créer un thread dans un processus de système d’exploitation Windows|[System::Threading::Thread::Start](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Exécuter des procédures d’arrêt `exit` (par exemple, vider les mémoires tampons), puis retourner le contrôle au programme appelant sans arrêter le processus|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|Exécuter des procédures d’arrêt `_exit`, puis redonner le contrôle au programme appelant sans arrêter le processus|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_cwait](../c-runtime-library/reference/cwait.md)|Attendre la fin d’un autre processus|[System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Terminer un thread de système d’exploitation Windows|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|Exécuter un nouveau processus avec une liste d’arguments|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|Exécuter un nouveau processus avec une liste d’arguments et un environnement donné|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Exécuter un nouveau processus en utilisant la variable `PATH` et une liste d’arguments|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Exécuter un nouveau processus en utilisant la variable `PATH`, un environnement donné et une liste d’arguments|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|Exécuter un nouveau processus avec un tableau d’arguments|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|Exécuter un nouveau processus avec un tableau d’arguments et un environnement donné|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Exécuter un nouveau processus en utilisant la variable `PATH` et un tableau d’arguments|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Exécuter un nouveau processus en utilisant la variable `PATH`, un environnement donné et un tableau d’arguments|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|Appeler des fonctions enregistrées par `atexit` et `_onexit`, vider toutes les mémoires tampons, fermer tous les fichiers ouverts et terminer le processus|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|Terminer le processus immédiatement sans appeler `atexit` ou `_onexit`, ou vider les mémoires tampons|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Obtenir la valeur de la variable d’environnement|[System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[_getpid](../c-runtime-library/reference/getpid.md)|Obtenir un numéro d’identification de processus|[System::Diagnostics::Process::Id](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Restaurer l’environnement de pile enregistré ; l’utiliser pour exécuter un `goto` non-local|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Planifier des routines à exécuter à l’arrêt du programme ; utiliser pour la compatibilité avec Microsoft C/C++ version 7.0 et antérieures|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_pclose](../c-runtime-library/reference/pclose.md)|Attendre un nouveau processeur de commandes et fermer le flux du canal associé|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|Imprimer un message d’erreur|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_pipe](../c-runtime-library/reference/pipe.md)|Créer un canal pour la lecture et l’écriture|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|Créer un canal et exécuter une commande|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Ajouter ou modifier la valeur de la variable d’environnement|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[raise](../c-runtime-library/reference/raise.md)|Envoyer un signal au processus appelant|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Enregistrer l’environnement de pile ; utiliser pour exécuter un `goto` non-local|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[signal](../c-runtime-library/reference/signal.md)|Gérer le signal d’interruption|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Créer un processus et l’exécuter avec la liste d’arguments spécifiée|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Créer un processus et l’exécuter avec la liste d’arguments et l’environnement spécifiés|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Créer un processus et l’exécuter en utilisant la variable `PATH` et une liste d’arguments spécifiée|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Créer un processus et l’exécuter en utilisant la variable `PATH`, l’environnement et la liste d’arguments spécifiés|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Créer un processus et l’exécuter avec le tableau d’arguments spécifié|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Créer un processus et l’exécuter avec le tableau d’arguments et l’environnement spécifiés|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Créer un processus et l’exécuter en utilisant la variable `PATH` et le tableau d’arguments spécifié|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Créer un processus et l’exécuter en utilisant la variable `PATH`, l’environnement et le tableau d’arguments spécifiés|[System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|Exécuter une commande de système d’exploitation|[System::Diagnostics::ProcessStartInfo, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process, classe](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Dans le système d’exploitation Windows, le processus généré équivaut au processus de génération. Tous les processus peuvent utiliser `_cwait` pour attendre un autre processus dont l’ID de processus est connu.  
  
 La différence entre les familles `_exec` et `_spawn` est qu’une fonction `_spawn` peut retourner le contrôle du nouveau processus au processus appelant. Dans une fonction `_spawn`, le processus appelant et le nouveau processus sont présents dans la mémoire, sauf si `_P_OVERLAY` est spécifié. Dans une fonction `_exec`, le nouveau processus se superpose au processus appelant. Le contrôle ne peut dont pas être retourné au processus appelant, sauf si une erreur se produit pendant la tentative de démarrage de l’exécution du nouveau processus.  
  
 Les différences entre les fonctions de la famille `_exec`, ainsi qu’entre celles de la famille `_spawn`, impliquent la méthode de localisation du fichier (à exécuter comme le nouveau processus), le formulaire dans lequel les arguments sont passés au nouveau processus et la méthode de définition de l’environnement, comme indiqué dans le tableau suivant. Utilisez une fonction qui passe une liste d’arguments quand le nombre d’arguments est constant ou connu au moment de la compilation. Utilisez une fonction qui passe un pointeur à un tableau contenant les arguments quand le nombre d’arguments doit être déterminé au moment de l’exécution. Les informations contenues dans le tableau suivant s’appliquent également aux caractères larges équivalents des fonctions `_spawn` et `_exec`.  
  
### <a name="spawn-and-exec-function-families"></a>Familles de fonctions _spawn et _exec  
  
|Fonctions|Utiliser la variable PATH pour localiser le fichier|Convention de passage d'argument|Paramètres d’environnement|  
|---------------|--------------------------------------|----------------------------------|--------------------------|  
|`_execl, _spawnl`|Non|Liste|Hérité du processus appelant|  
|`_execle, _spawnle`|Non|Liste|Pointeur vers la table d’environnement pour le nouveau processus passé comme dernier argument|  
|`_execlp, _spawnlp`|Oui|Liste|Hérité du processus appelant|  
|`_execlpe, _spawnlpe`|Oui|Liste|Pointeur vers la table d’environnement pour le nouveau processus passé comme dernier argument|  
|`_execv, _spawnv`|Non|Tableau|Hérité du processus appelant|  
|`_execve, _spawnve`|Non|Tableau|Pointeur vers la table d’environnement pour le nouveau processus passé comme dernier argument|  
|`_execvp, _spawnvp`|Oui|Tableau|Hérité du processus appelant|  
|`_execvpe, _spawnvpe`|Oui|Tableau|Pointeur vers la table d’environnement pour le nouveau processus passé comme dernier argument|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
