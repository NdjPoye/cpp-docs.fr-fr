---
title: "DLL non-MFC : Vue d’ensemble | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce755f88e8a9efaaacd456206d599dd5db75443
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="non-mfc-dlls-overview"></a>DLL non-MFC : vue d'ensemble
Une DLL non - MFC est une DLL qui n’utilise pas MFC en interne, et les fonctions exportées de la DLL peuvent être appelées par les fichiers exécutables MFC ou non-MFC. Les fonctions sont généralement exportées d’une DLL non - MFC à l’aide de l’interface C standard.  
  
 Pour plus d’informations sur les DLL non - MFC, consultez [Dynamic-Link Libraries](http://msdn.microsoft.com/library/windows/desktop/ms682589) dans le [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
## <a name="what-do-you-want-to-do"></a>Que voulez-vous faire ?  
  
-   [Procédure pas à pas : Création et utilisation d’une bibliothèque de liens dynamiques](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
  
-   [Exporter à partir d’une DLL](../build/exporting-from-a-dll.md)  
  
-   [Lier un exécutable à une DLL](../build/linking-an-executable-to-a-dll.md)  
  
-   [Initialiser une DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
  
-   [DLL MFC normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL MFC normales liées dynamiquement à MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL d’extension de MFC : vue d’ensemble](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Genres de DLL](../build/kinds-of-dlls.md)