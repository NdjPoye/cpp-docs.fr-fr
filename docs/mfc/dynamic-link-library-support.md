---
title: "Prise en charge de la bibliothèque de liens dynamiques | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- regular MFC DLLs [MFC], project targets as DLLs
- DLLs [MFC], MFC
- NAFXDW.LIB
- MFC DLLs [MFC], regular MFC DLLs
- USRDLLs, DLL support
- NAFXDWD.LIB
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 394c48644c3b5cdc2514fefef2f4451e4098856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="dynamic-link-library-support"></a>Prise en charge des bibliothèques de liens dynamiques
Les bibliothèques NAFXCW.lib et NAFXCWD.lib (répertoriées dans le tableau des Conventions de nom de bibliothèque de liaison statique dans [Conventions d’affectation de noms de la bibliothèque](../mfc/library-naming-conventions.md)) créer votre projet en tant qu’une bibliothèque de liens dynamiques, appelée une « DLL régulière MFC » (anciennement « USRDLL ») qui peut être utilisé avec les applications ne pas été générées avec la bibliothèque de classes. Cette prise en charge de la DLL n’est pas identique à MFCx0.DLL et de MFCx0D.DLL (appelée AFXDLL), qui contiennent la bibliothèque de classes complète dans une DLL. Pour plus d’informations, consultez [DLL](../build/dlls-in-visual-cpp.md). Pour un tableau des noms de DLL, consultez [les Conventions d’affectation de noms pour les DLL MFC](../build/naming-conventions-for-mfc-dlls.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)

