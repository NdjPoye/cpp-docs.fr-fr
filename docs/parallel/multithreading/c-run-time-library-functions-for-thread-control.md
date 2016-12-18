---
title: "Fonctions des biblioth&#232;ques Runtime C pour le contr&#244;le des threads | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "_beginthread (fonction)"
  - "_beginthreadex (fonction)"
  - "_endthread (fonction)"
  - "_endthreadex (fonction)"
  - "multithreading (C++), contrôler les threads"
  - "threads (C++), contrôler les threads"
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions des biblioth&#232;ques Runtime C pour le contr&#244;le des threads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Tous les programmes Win32 possèdent au moins un thread.  Un thread peut créer des threads supplémentaires.  Il peut aussi accomplir sa tâche rapidement puis s'arrêter, ou rester actif pendant toute la durée de vie du programme.  
  
 Les bibliothèques Runtime C LIBCMT et MSVCRT fournissent les fonctions suivantes pour la création et la suspension des threads : [\_beginthread, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) et [\_endthread, \_endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md).  
  
 Les fonctions `_beginthread` et `_beginthreadex` créent un nouveau thread et retournent un identificateur de thread si l'opération se déroule correctement.  Le thread s'arrête automatiquement à la fin de l'exécution, ou il peut s'arrêter avec un appel à `_endthread` ou `_endthreadex`.  
  
> [!NOTE]
>  Si vous pensez appeler des routines d'exécution du C à partir d'un programme créé à l'aide de Libcmt.lib, vous devez démarrer vos threads à l'aide de la fonction `_beginthread` ou `_beginthreadex`.  N'utilisez pas les fonctions Win32 `ExitThread` et `CreateThread`.  L'utilisation de `SuspendThread` peut se traduire par un interblocage si plusieurs threads restent bloqués en attendant que le thread suspendu mette fin à son accès à une structure de données d'exécution du C.  
  
##  <a name="_core_the__beginthread_function"></a> Fonctions \_beginthread et \_beginthreadex  
 Les fonctions `_beginthread` et `_beginthreadex` créent un nouveau thread.  Un thread partage les segments du code et des données d'un processus avec les autres threads du processus, mais possède ses propres valeurs de registres uniques, espace de pile et adresse d'instructions.  Le système alloue des tranches du temps de l'UC à chaque thread, ce qui autorise une exécution simultanée de tous les threads d'un processus.  
  
 Les fonctions `_beginthread` et `_beginthreadex` sont semblables à la fonction [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) dans l'API Win32, mais elles présentent les différences suivantes :  
  
-   Elles initialisent certaines variables de la bibliothèque Runtime C.  Ceci est important uniquement si vous utilisez la bibliothèque Runtime C dans vos threads.  
  
-   `CreateThread` permet de contrôler les attributs de sécurité.  Vous pouvez utiliser cette fonction pour démarrer un thread dans un état suspendu.  
  
 Les fonctions `_beginthread` et `_beginthreadex` retournent un handle au nouveau thread en cas de réussite ou un code d'erreur en cas d'erreur.  
  
##  <a name="_core_the__endthread_function"></a> Fonctions \_endthread et \_endthreadex  
 La fonction [\_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) met fin à un thread créé par `_beginthread` \(et de la même façon, `_endthreadex` met fin à un thread créé par `_beginthreadex`\).  Les threads se terminent automatiquement lorsqu'ils finissent.  `_endthread` et `_endthreadex` sont utiles pour un arrêt conditionnel dans un thread.  Un thread dédié au traitement des communications, par exemple, peut s'arrêter s'il n'est pas en mesure de prendre le contrôle du port de communication.  
  
## Voir aussi  
 [Multithreading à l'aide de C et de Win32](../../parallel/multithreading-with-c-and-win32.md)