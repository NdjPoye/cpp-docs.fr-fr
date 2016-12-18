---
title: "Erreur d&#39;ex&#233;cution C R6016 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6016"
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
caps.latest.revision: 12
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur d&#39;ex&#233;cution C R6016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

espace insuffisant pour les données du thread  
  
> [!NOTE]
>  Si vous rencontrez ce message d'erreur, cela signifie que le programme nommé a été arrêté en raison d'un problème de mémoire interne.  Il peut y avoir plusieurs raisons à cette erreur, mais bien souvent elle est provoquée par un défaut du programme ou par l'altération des bibliothèques Visual C\+\+ qu'il utilise.  
>   
>  Vous pouvez essayer de suivre les étapes ci\-après pour corriger cette erreur :  
>   
>  -   Utilisez la page **Programmes et fonctionnalités** du **Panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Utilisez la page **Programmes et fonctionnalités** du **Panneau de configuration** pour réparer ou réinstaller toutes les copies de Microsoft Visual C\+\+ Redistributable.  
> -   Vérifiez les mises à jour logicielles via **Windows Update** dans le **Panneau de configuration**.  
> -   Recherchez une version mise à jour du programme.  
  
 Cette erreur se produit, car le programme n'a pas reçu suffisamment de mémoire de la part du système d'exploitation pour effectuer un appel [\_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) ou `_beginthreadex`, ou le stockage local des threads n'a pas été initialisé par `_beginthread` ou `_beginthreadex`.  
  
 Quand un nouveau thread est lancé, la bibliothèque doit créer une base de données interne pour le thread.  Si la base de données ne peut pas être étendue à l'aide de la mémoire fournie par le système d'exploitation, le thread ne démarre pas et le processus d'appel s'arrête.  Cela peut se produire lorsque de trop nombreux threads ont été créés par le processus, ou si le stockage local des threads est épuisé.  
  
 Il est recommandé qu'un exécutable qui appelle la bibliothèque Runtime C \(CRT\) utilise `_beginthreadex` pour la création de threads plutôt que l'API Windows `CreateThread`.  `_beginthreadex` initialise le stockage statique interne utilisé par de nombreuses fonctions CRT dans le stockage local des threads.  Si vous utilisez `CreateThread` pour créer un thread, la bibliothèque Runtime C \(CRT\) peut terminer le processus avec R6016 lorsqu'un appel est effectué à destination d'une fonction CRT qui nécessite l'initialisation du stockage statique interne.