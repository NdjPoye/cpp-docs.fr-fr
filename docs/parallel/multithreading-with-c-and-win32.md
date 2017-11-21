---
title: "Multithreading à l’aide de C et Win32 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0e2ce9377d0ea4b2bd7b04255eb1c8099341af39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="multithreading-with-c-and-win32"></a>Multithreading à l'aide de C et de Win32
Microsoft Visual C++ prend en charge la création d’applications multithread avec Microsoft Windows : Windows XP, Windows 2000, Windows NT, Windows Millennium Edition et Windows 98. Vous devez envisager d’utiliser plusieurs threads si votre application doit gérer plusieurs activités, telles que simultanées au clavier et d’entrée de la souris. Un thread peut traiter l’entrée au clavier pendant un deuxième thread filtre les activités de la souris. Un troisième thread peut mettre à jour l’écran d’affichage en fonction des données à partir de threads de la souris et clavier. En même temps, les autres threads peuvent accéder aux fichiers de disque ou obtenir des données à partir d’un port de communication.  
  
 Avec Visual C++, il existe deux façons de programme avec plusieurs threads : utiliser la bibliothèque Microsoft Foundation classes (MFC) ou de la bibliothèque Runtime C et de l’API Win32. Pour plus d’informations sur la création d’applications multithread avec MFC, consultez [Multithreading à l’aide de C++ et MFC](../parallel/multithreading-with-cpp-and-mfc.md) après avoir lu les rubriques suivantes consacrées au multithreading dans C.  
  
 Ces rubriques expliquent les fonctionnalités de Visual C++ qui prennent en charge la création de programmes multithread.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
  
-   [Ce que le multithreading est sur le](../parallel/multithread-programs.md)  
  
-   [Prise en charge de la bibliothèque pour le multithreading](../parallel/library-support-for-multithreading.md)  
  
-   [Les fichiers Include pour le multithreading](../parallel/include-files-for-multithreading.md)  
  
-   [Fonctions de la bibliothèque Runtime C pour le contrôle du thread](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [Exemple de programme multithread en C](../parallel/sample-multithread-c-program.md)  
  
-   [Écriture d’un programme Win32 Multithread](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [Compilation et liaison de programmes multithread](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [Éviter les problèmes avec les programmes multithread](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [Stockage local des threads (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge du multithreading pour le code plus ancien (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)