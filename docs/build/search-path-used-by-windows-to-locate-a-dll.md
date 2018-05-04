---
title: Rechercher le chemin d’accès utilisé par Windows pour retrouver une DLL | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- searching [C++], DLLs
- DLLs [C++], Windows search path
- Windows [C++], DLL search path
- known DLL searches [C++]
- locating DLLs
- finding DLLs
- search paths [C++]
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 166b5fccf6dd231029f79fede837909a49e7fc4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="search-path-used-by-windows-to-locate-a-dll"></a>Chemin de recherche utilisé par Windows pour localiser une DLL
Avec la liaison d’implicites et explicites, Windows recherche d’abord « DLL connues », telles que Kernel32.dll et User32.dll. Windows recherche ensuite les DLL dans l’ordre suivant :  
  
1.  Le répertoire où se trouve le module exécutable du processus en cours.  
  
2.  Le répertoire actif.  
  
3.  Le répertoire du système Windows. Le **GetSystemDirectory** fonction récupère le chemin d’accès de ce répertoire.  
  
4.  Le répertoire Windows. Le **GetWindowsDirectory** fonction récupère le chemin d’accès de ce répertoire.  
  
5.  Les répertoires énumérés dans la variable d’environnement PATH.  
  
    > [!NOTE]
    >  La variable d’environnement LIBPATH n’est pas utilisée.  
  
## <a name="what-do-you-want-to-do"></a>Que voulez-vous faire ?  
  
-   [Comment lier de manière implicite à une DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Comment lier de manière explicite à une DLL](../build/linking-an-executable-to-a-dll.md#linking-explicitly)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="see-also"></a>Voir aussi  
 [DLL dans Visual C++](../build/dlls-in-visual-cpp.md)