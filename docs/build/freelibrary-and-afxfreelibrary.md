---
title: FreeLibrary et AfxFreeLibrary | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs:
- C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1e1bf5f1a05438ddf89af86c9b0d12e7885b901
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary et AfxFreeLibrary
Processus de liaison explicite avec un appel DLL le [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) fonctionner lorsque le module DLL n’est plus nécessaire. Cette fonction décrémente le nombre de module référence et, si le décompte de références est égal à zéro, annule le mappage à partir de l’espace d’adressage du processus.  
  
 Dans une application MFC, utilisez [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) au lieu de `FreeLibrary` pour décharger une DLL d’extension MFC. L’interface (prototype de fonction) pour `AfxFreeLibrary` est identique à `FreeLibrary`.  
  
## <a name="what-do-you-want-to-do"></a>Que voulez-vous faire ?  
  
-   [Comment lier de manière implicite à une DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
  
-   [LoadLibrary et AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>Voir aussi  
 [DLL en Visual C++](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)