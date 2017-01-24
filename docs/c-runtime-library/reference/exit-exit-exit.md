---
title: "exit, _Exit, _exit | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_exit"
  - "exit"
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
  - "Exit"
  - "_exit"
  - "process/exit"
  - "process/_Exit"
  - "stdlib/exit"
  - "stdlib/_Exit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "exit (fonction)"
  - "_exit (fonction)"
  - "processus, terminer"
  - "appels de fonction, terminer"
  - "arrêt des processus, appeler"
ms.assetid: b1501fa6-27c2-478c-9e93-cc4fd802a01f
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exit, _Exit, _exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Termine le processus appelant. La fonction `exit` le termine après nettoyage ; `_exit` et `_Exit` le terminent immédiatement.  
  
> [!NOTE]
>  N’utilisez pas cette méthode pour terminer une application de plateforme Windows universelle ou une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], sauf dans des scénarios de test ou de débogage. Les méthodes par programmation ou via l’interface utilisateur pour fermer une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ne sont pas autorisées. Pour plus d’informations sur les applications Windows 8 et 8.1, consultez [Cycle de vie des applications](http://go.microsoft.com/fwlink/?LinkId=262853). Pour plus d’informations sur les applications Windows 10, consultez [Guides de procédures pour les applications Windows 10](http://go.microsoft.com/fwlink/p/?linkid=619133).  
  
## Syntaxe  
  
```  
void exit(   
   int const status   
);  
void _Exit(   
   int const status   
);  
void _exit(   
   int const status   
);  
```  
  
#### Paramètres  
 `status`  
 Code d’état de sortie.  
  
## Notes  
 Les fonctions `exit`, `_Exit` et `_exit` terminent le processus appelant. La fonction `exit` appelle des destructeurs pour les objets locaux de thread, puis appelle, selon un ordre dernier entré premier sorti \(LIFO\), les fonctions qui sont inscrites par `atexit` et `_onexit`, puis vide toutes les mémoires tampons de fichiers avant de terminer le processus. Les fonctions `_Exit` et `_exit` terminent le processus sans détruire les objets locaux de thread ou sans traiter les fonctions `atexit` ou `_onexit`, et sans vider les mémoires tampons des flux.  
  
 Bien que les appels de `exit`, `_Exit` et `_exit` ne retournent pas de valeur, l’octet de poids faible de `status` est rendu disponible pour l’environnement hôte ou le processus appelant en attente, s’il existe, une fois le processus terminé. En règle générale, l’appelant définit `status` sur 0 pour indiquer une sortie normale, ou sur une autre valeur pour indiquer une erreur. La valeur de `status` est disponible pour la commande batch du système d’exploitation `ERRORLEVEL` et est représentée par une de ces deux constantes : `EXIT_SUCCESS`, qui représente la valeur 0, ou `EXIT_FAILURE`, qui représente la valeur 1.  
  
 Les fonctions `exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit` et `_c_exit` se comportent comme suit.  
  
|Fonction|Description|  
|--------------|-----------------|  
|`exit`|Exécute les procédures d’arrêt complètes de la bibliothèque C, termine le processus et indique le code d’état fourni à l’environnement hôte.|  
|`_Exit`|Exécute les procédures d’arrêt minimales de la bibliothèque C, termine le processus et indique le code d’état fourni à l’environnement hôte.|  
|`_exit`|Exécute les procédures d’arrêt minimales de la bibliothèque C, termine le processus et indique le code d’état fourni à l’environnement hôte.|  
|`quick_exit`|Exécute les procédures d’arrêt rapides de la bibliothèque C, termine le processus et indique le code d’état fourni à l’environnement hôte.|  
|`_cexit`|Exécute les procédures d’arrêt complètes de la bibliothèque C et retourne à l’appelant. Ne termine pas le processus.|  
|`_c_exit`|Exécute les procédures d’arrêt minimales de la bibliothèque C et retourne à l’appelant. Ne termine pas le processus.|  
  
 Quand vous appelez la fonction `exit`, `_Exit` ou `_exit`, les destructeurs pour les objets temporaires ou automatiques qui existent au moment de l’appel ne sont pas appelés. Un objet automatique est défini dans une fonction où l’objet n’est pas déclaré comme statique. Un objet temporaire est un objet qui est créé par le compilateur. Pour détruire un objet automatique avant d’appeler `exit`, `_Exit` ou `_exit`, appelez explicitement le destructeur de l’objet, comme suit :  
  
```  
myObject.myClass::~myClass();  
```  
  
 N’utilisez pas `DLL_PROCESS_ATTACH` pour appeler `exit` depuis `DllMain`. Si vous voulez quitter la fonction `DLLMain`, retournez `FALSE` depuis `DLL_PROCESS_ATTACH`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`exit`, `_Exit`, `_exit`|\<process.h\> ou \<stdlib.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_exit.c // This program returns an exit code of 1. The // error code could be tested in a batch file. #include <stdlib.h> int main( void ) { exit( 1 ); }  
```  
  
## Équivalent .NET Framework  
 [System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_cexit, \_c\_exit](../../c-runtime-library/reference/cexit-c-exit.md)   
 [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [quick\_exit](../../c-runtime-library/reference/quick-exit1.md)   
 [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)