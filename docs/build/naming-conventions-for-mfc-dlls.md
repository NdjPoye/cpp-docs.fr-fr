---
title: "Conventions d’affectation de noms pour les DLL MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC libraries [C++], naming conventions
- naming conventions [C++], MFC DLLs
- MFC DLLs [C++], naming conventions
- libraries [C++], MFC DLL names
- shared DLL versions [C++]
- DLLs [C++], naming conventions
- DLLs [C++], library names
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f7702e9babcc4769136d6deab63b627f8b09bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="naming-conventions-for-mfc-dlls"></a>Conventions d'affectation de noms pour les DLL MFC
Les DLL et les bibliothèques incluses dans les MFC suivent une convention d’affectation de noms structurée. Cela rend plus facile de savoir quelle DLL ou la bibliothèque, vous devez utiliser à cette fin.  
  
 Les bibliothèques d’importation nécessaires pour générer des applications ou des DLL d’extension MFC qui utilisent ces DLL ont le même nom que la DLL, mais ont une extension de nom de fichier .lib.  
  
### <a name="shared-dll-naming-convention"></a>Convention d’affectation de noms de DLL partagée  
  
|DLL|Description|  
|---------|-----------------|  
|MFCx0.DLL|DLL MFC, version Release de ANSI|  
|MFCx0U.DLL|DLL MFC, version Release d’Unicode|  
|MFCx0D.DLL|DLL MFC, version de débogage ANSI|  
|MFCx0UD.DLL|DLL MFC, version Unicode Debug|  
  
 Si vous liez dynamiquement à la version DLL partagée de MFC, s’il s’agit d’une application ou d’une DLL d’extension MFC, vous devez inclure MFCx0.DLL avec votre produit. Si vous avez besoin de prise en charge Unicode dans votre application, incluez MFCx0U.DLL à la place.  
  
 Si vous effectuez une liaison statique votre DLL de MFC, vous devez le lier avec l’une des bibliothèques statiques MFC. Ces versions sont nommées conformément à la convention [N &#124; U] AFXCW [D]. LIB. Pour plus d’informations, consultez le tableau « Conventions d’affectation de noms de liaison statique bibliothèque » dans [Conventions d’affectation de noms de la bibliothèque](../mfc/library-naming-conventions.md) (MFC).  
  
 Pour obtenir la liste des DLL Visual C++ qui peuvent être distribués avec vos applications, consultez Redist.txt dans votre installation de Visual Studio.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
  
-   [La convention d’affectation de noms pour les bibliothèques](../mfc/library-naming-conventions.md)  
  
## <a name="see-also"></a>Voir aussi  
 [DLL dans Visual C++](../build/dlls-in-visual-cpp.md)