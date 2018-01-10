---
title: Prise en charge le multithreading pour un Code plus ancien (Visual C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1037b8b81c9286ac1b1dd9303294b4300e7c9309
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Prise en charge du multithreading pour le code plus ancien (Visual C++)
Visual C++ vous permet d’avoir plusieurs threads simultanés d’exécution en cours d’exécution simultanément. Avec le multithreading, vous pouvez exécuter les tâches en arrière-plan, gérer des flux simultanés d’entrées, gérer une interface utilisateur et bien plus encore.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Multithreading à l’aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)  
 Fournit la prise en charge pour la création d’applications multithread avec Microsoft Windows  
  
 [Multithreading à l’aide de C++ et de MFC](../parallel/multithreading-with-cpp-and-mfc.md)  
 Décrit ce que sont les processus et les threads et approche à la bibliothèque MFC multithreading est.  
  
 [Multithreading et paramètres régionaux](../parallel/multithreading-and-locales.md)  
 Décrit les problèmes qui surviennent lors de l’utilisation de la fonctionnalité de paramètres régionaux de la bibliothèque Runtime C et la bibliothèque C++ Standard dans une application multithread.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 Représente un thread d'exécution dans une application.  
  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Décrit une classe virtuelle pure qui fournit une fonctionnalité commune aux objets de synchronisation dans Win32.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Représente un sémaphore, qui est un objet de synchronisation qui permet à un nombre limité de threads dans un ou plusieurs processus d’accéder à une ressource.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Représente un mutex, un objet de synchronisation qui permet à un thread l’accès mutuellement exclusif à une ressource.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Représente une section critique, qui est un objet de synchronisation qui permet à un seul thread à la fois pour accéder à une ressource ou une section de code.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Représente un événement, qui est un objet de synchronisation qui permet à un thread de notifier à un autre qu’un événement s’est produit.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 Représente le mécanisme de contrôle d'accès utilisé pour accéder aux ressources dans un programme multithread.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 Représente le mécanisme de contrôle d'accès utilisé dans le contrôle de l'accès à une ressource dans un programme multithread.  
  
 [(NOTINBUILD) Méthodologies de programmation Visual C++](http://msdn.microsoft.com/en-us/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Fournit des liens vers des rubriques qui fournissent des informations conceptuelles sur les bibliothèques Visual C++ et des rubriques qui traitent des différentes technologies et techniques de codage.