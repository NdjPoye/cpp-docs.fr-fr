---
title: "Contr&#244;le de processus et d&#39;environnement | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "routines de contrôle de l'environnement"
  - "processus parent"
  - "routines de contrôle de processus"
  - "processus, tâches d'administration"
  - "processus, démarrer"
  - "processus, arrêter"
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Contr&#244;le de processus et d&#39;environnement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les routines de régulation de processus pour démarrer, arrêter, et gérer des processus depuis un programme.  Utilisez les routines d'environnement\-contrôle pour obtenir et modifier les informations sur l'environnement du système d'exploitation.  
  
### Fonctions de contrôle de processus et d'environnement  
  
|Routine|Utilisez|Équivalent de .NET Framework|  
|-------------|--------------|----------------------------------|  
|[abort](../c-runtime-library/reference/abort.md)|Arrêter le processus sans vider les mémoires tampons ou appeler des fonctions enregistrées par `atexit` et `_onexit`|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Test d'une erreur de logique|[\<caps:sentence id\="tgt14" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|macros [\_ASSERT, \_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Similaire à `assert`, mais uniquement disponible dans les versions de débogage des bibliothèques Runtime|[\<caps:sentence id\="tgt17" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|Routines de planification pour l'exécution à l'arrêt du programme|[\<caps:sentence id\="tgt20" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Créez un nouveau thread sur un processus de système d'exploitation Windows|[\<caps:sentence id\="tgt23" sentenceid\="221e38ecc6535bce91af4e1a19f464d1" class\="tgtSentence"\>System::Threading::Thread::Start\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[\_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Effectue les procédures d'arrêt `exit` \(telles que vider les mémoires tampons\), puis retourne le contrôle au programme appelant sans mettre fin au processus|[\<caps:sentence id\="tgt26" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_c\_exit](../c-runtime-library/reference/cexit-c-exit.md)|Effectue les procédures d'arrêt `_exit`, puis retourne le contrôle au programme appelant sans mettre fin au processus|[\<caps:sentence id\="tgt29" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_cwait](../c-runtime-library/reference/cwait.md)|Attendre qu'un autre processus se termine.|[\<caps:sentence id\="tgt32" sentenceid\="d9c88c429eaacaa9f37d91d29bc6504e" class\="tgtSentence"\>System::Diagnostics::Process::WaitForExit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[\_endthread, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Terminer un thread de système d'exploitation Windows|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_execl, \_wexecl](../c-runtime-library/reference/execl-wexecl.md)|Exécute le nouveau processus avec la liste d'arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execle, \_wexecle](../c-runtime-library/reference/execle-wexecle.md)|Exécutez le nouveau processus avec la liste d'arguments et l'environnement donné|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlp, \_wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Exécutez le nouveau processus avec la variable `PATH` et la liste des arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlpe, \_wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Exécutez le nouveau processus avec la variable `PATH`, l'environnement donné, et la liste d'arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execv, \_wexecv](../c-runtime-library/reference/execv-wexecv.md)|Exécute le nouveau processus avec le tableau d'arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execve, \_wexecve](../c-runtime-library/reference/execve-wexecve.md)|Exécutez le nouveau processus avec le tableau d'arguments et l'environnement donné|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvp, \_wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Exécutez le nouveau processus avec la variable `PATH` et le tableau des arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvpe, \_wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Exécutez le nouveau processus avec la variable `PATH`, l'environnement donné, et le tableau d'arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|Appelle les fonctions stockées par `atexit` et `_onexit`, vide toutes les mémoires tampons, ferme tous les fichiers ouverts, et termine le processus|[\<caps:sentence id\="tgt64" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[\_exit](../c-runtime-library/reference/exit-exit-exit.md)|Termine le processus immédiatement sans appeler `atexit` ou `_onexit` ou vider les mémoires tampons|[\<caps:sentence id\="tgt67" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Obtient la valeur de la variable d'environnement|[\<caps:sentence id\="tgt70" sentenceid\="795988b9277d74ea3b722ecd42dcb29d" class\="tgtSentence"\>System::Environment::GetEnvironmentVariable\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[\_getpid](../c-runtime-library/reference/getpid.md)|Obtient le numéro d'identification de processus|[\<caps:sentence id\="tgt73" sentenceid\="745b82c461dc74b15540e9622f7cd7bd" class\="tgtSentence"\>System::Diagnostics::Process::Id\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Restaure l'environnement de pile sauvegardé ; l'utilise pour exécuter un `goto` non local|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Routines de planification pour l'exécution à l'arrêt du programme ; utilisation pour la compatibilité avec la version 7,0 de Microsoft C\/C\+\+ et antérieures|[\<caps:sentence id\="tgt81" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_pclose](../c-runtime-library/reference/pclose.md)|Attendez le nouveau processeur de commandes et fermez le flux de données sur le canal associé|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[perror, \_wperror](../c-runtime-library/reference/perror-wperror.md)|Imprime un message d'erreur.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_pipe](../c-runtime-library/reference/pipe.md)|Créez un canal pour lire et écrire|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md)|Créez le canal et exécutez la commande|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md), [\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Ajoutez ou modifiez la valeur de la variable d'environnement|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[raise](../c-runtime-library/reference/raise.md)|Envoyer le signal au processus appelant|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Enregistrez l'environnement de pile ; utilisez le pour exécuter un `goto`non local|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[signal](../c-runtime-library/reference/signal.md)|Signal d'interruption de descripteur|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_spawnl, \_wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Créer et exécuter un nouveau processus avec la liste d'arguments spécifiée|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnle, \_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Créer et exécuter un nouveau processus avec la liste d'arguments spécifiée et l'environnement|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlp, \_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Créer et exécuter un nouveau processus avec la variable `PATH` et la liste des arguments spécifiée|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlpe, \_wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Créer et exécuter un nouveau processus avec la variable `PATH`, l'environnement spécifié et la liste des arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnv, \_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Créer et exécuter un nouveau processus avec le tableau d'arguments spécifiée|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnve, \_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Créer et exécuter un nouveau processus avec le tableau d'arguments et l'environnement spécifié|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvp, \_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Créer et exécuter un nouveau processus avec la variable `PATH` et le tableau des arguments spécifiée|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvpe, \_wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Créer et exécuter un nouveau processus avec la variable `PATH`, l'environnement spécifié et le tableau des arguments|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system, \_wsystem](../c-runtime-library/reference/system-wsystem.md)|Exécutez la commande du système d'exploitation|[System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Dans le système d'exploitation Windows, le processus engendré est équivalent au processus engendrant.  Tout processus peut utiliser `_cwait` pour attendre tout autre processus dont l'ID de processus est connu.  
  
 La différence entre `_exec` et les familles `_spawn` est qu'une fonction `_spawn` peut retourner le contrôle depuis le nouveau processus vers le processus appelant.  Dans une fonction `_spawn`, le processus appelant et le nouveau processus sont présents dans la mémoire à moins que `_P_OVERLAY` soit spécifié.  Dans une fonction `_exec`, le nouveau processus recouvre le processus appelant, le contrôle ne peut pas retourner au processus appelant sauf si une erreur se produit dans la tentative de démarrage de l'exécution du nouveau processus.  
  
 Les différences entre les fonctions dans la famille `_exec`, ainsi que celles parmi la famille `_spawn`, comprennent la méthode de recherche du fichier à exécuter comme le nouveau processus, le formulaire dans lequel les arguments sont passés au nouveau processus, puis la méthode pour définir l'environnement, comme indiqué dans le tableau suivant.  Utilisez une fonction qui passe une liste d'arguments lorsque le nombre d'arguments est fixe ou est connu au moment de compiler  Utilisez une fonction qui passe un pointeur vers un tableau qui contient les arguments lorsque le nombre d'arguments doit être déterminé au moment de l'exécution.  Les informations dans le tableau ci\-dessous s'appliquent également aux homologues de caractères étendus de `_spawn` et `_exec` s'exécute.  
  
### Les familles de fonctions \_spawn et le \_exec  
  
|Fonctions|Utilisez la variable PATH pour rechercher le fichier|Convention de passage d'argument|paramètres d'environnement|  
|---------------|----------------------------------------------------------|--------------------------------------|--------------------------------|  
|`_execl, _spawnl`|Non|Liste|Hérité du processus appelant|  
|`_execle, _spawnle`|Non|Liste|Le pointeur vers la table d'environnement pour le nouveau processus est transmis en tant que dernier argument|  
|`_execlp, _spawnlp`|Oui|Liste|Hérité du processus appelant|  
|`_execlpe, _spawnlpe`|Oui|Liste|Le pointeur vers la table d'environnement pour le nouveau processus est transmis en tant que dernier argument|  
|`_execv, _spawnv`|Non|Tableau|Hérité du processus appelant|  
|`_execve, _spawnve`|Non|Tableau|Le pointeur vers la table d'environnement pour le nouveau processus est transmis en tant que dernier argument|  
|`_execvp, _spawnvp`|Oui|Tableau|Hérité du processus appelant|  
|`_execvpe, _spawnvpe`|Oui|Tableau|Le pointeur vers la table d'environnement pour le nouveau processus est transmis en tant que dernier argument|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)