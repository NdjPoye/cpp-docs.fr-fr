---
title: "abort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "abort"
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
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort (fonction)"
  - "abandonner le processus actuel"
  - "processus, abandonner"
ms.assetid: a797783b-40ed-4bdb-a2cd-14ffede39e8a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# abort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abandonne le processus actuel et retourne un code d'erreur.  
  
> [!NOTE]
>  N'utilisez pas cette méthode pour arrêter une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], sauf dans les scénarios de test ou de débogage.  Les méthodes de programmation ou de l'interface utilisateur pour fermer une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ne sont pas autorisées selon les [Critères de certification pour les applications Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889).  Pour plus d'informations, consultez [Cycle de vie d'une application \(applications du Windows Store\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Syntaxe  
  
```  
void abort( void );  
```  
  
## Valeur de retour  
 `abort` ne retourne pas de contrôle au processus appelant.  Par défaut, il recherche un gestionnaire de signal d'arrêt et déclenche un `SIGABRT` si un est défini.  Puis `abort` met fin au processus actuel et retourne un code de sortie au processus parent.  
  
## Notes  
 **Spécifique à Microsoft**  
  
 Par défaut, lorsqu'une application est générée avec la bibliothèque d'exécution de débogage, la routine `abort` affiche un message d'erreur avant que `SIGABRT` soit déclenché.  Pour les applications de console s'exécutant en mode de console, le message est envoyé à `STDERR`.  Les applications de bureau Windows et les applications console en mode fenêtré affichent le message dans une zone dédiée.  Pour supprimer le message, utilisez [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md) pour supprimer l'indicateur `_WRITE_ABORT_MSG`.  Le message affiché dépend de la version de l'environnement d'exécution utilisé.  Pour les applications générées en utilisant la version la plus récente de Visual C\+\+, le message se présente comme suit :  
  
 `R6010`  
  
 `- abort() has been called`  
  
 Dans les versions antérieures de la bibliothèque Runtime C, le message suivant était affiché :  
  
 "`This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information.`"  
  
 Lorsque le programme est compilé en mode débogage, le message affiche les options **Abandonner**, **Réessayer** ou **Ignorer**.  Si l'utilisateur choisit **Abandonner**, le programme se termine immédiatement et retourne le code de sortie 3.  Si l'utilisateur choisit **Réessayer**, un débogueur est appelé pour le débogage juste\-à\-temps, s'il est disponible.  Si l'utilisateur choisit **Ignorer**, `abort` continue le traitement normal.  
  
 Dans les versions commerciales ou de débogage, `abort` vérifie ensuite si un gestionnaire de signal d'arrêt est défini.  Si un gestionnaire de signal non défini par défaut est défini, `abort` appelle `raise(SIGABRT)`.  Utilisez la fonction [signal](../../c-runtime-library/reference/signal.md) pour associer une fonction gestionnaire de signal d'arrêt avec le signal `SIGABRT`.  Vous pouvez effectuer des actions personnalisées – par exemple, nettoyer les ressources ou enregistrer les informations – et arrêter l'application avec votre propre code d'erreur dans la fonction du gestionnaire.  Si aucun gestionnaire de signal personnalisé n'est défini, `abort` ne déclenche pas le signal `SIGABRT`.  
  
 Par défaut, dans les builds non débogage des applications de bureau ou de console, `abort` appelle ensuite le mécanisme de signalement d'erreurs Windows .  Watson\) pour signaler les défaillances à Microsoft.  Ce comportement peut être activé ou désactivé en appelant `_set_abort_behavior` et en définissant ou en masquant l'indicateur `_CALL_REPORTFAULT`.  Lorsque l'indicateur est défini, Windows affiche un message qui comporte un texte comme « Un problème est à l'origine du dysfonctionnement du programme. » L'utilisateur peut choisir d'appeler un débogueur avec un bouton **Déboguer**, ou choisir le bouton **Fermer le programme** pour terminer l'application avec un code d'erreur défini par le système d'exploitation.  
  
 Si le gestionnaire de rapport d'erreurs Windows n'est pas appelé, `abort` appelle [\_exit](../../c-runtime-library/reference/exit-exit-exit.md) pour arrêter le processus avec le code de sortie 3 et retourne le contrôle au processus parent ou au système d'exploitation.  `_exit` ne vide pas les mémoires tampons de flux ou effectue le traitement `atexit`\/`_onexit`.  
  
 Pour plus d'informations sur le débogage CRT, consultez [Techniques de débogage CRT](../Topic/CRT%20Debugging%20Techniques.md).  
  
 **Fin spécifique à Microsoft**  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`abort`|\<process.h\> ou \<stdlib.h\>|  
  
## Exemple  
 Le programme suivant essaie d'ouvrir un fichier et s'arrête si la tentative échoue.  
  
```c  
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
  
  **Le fichier n'a pas pu être ouvert : fichier ou répertoire inexistant**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Utilisation de abort](../../cpp/using-abort.md)   
 [abort, fonction](../../c-language/abort-function-c.md)   
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [\_DEBUG](../../c-runtime-library/debug.md)   
 [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md)