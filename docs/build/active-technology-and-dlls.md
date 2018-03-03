---
title: Technologie active et DLL | Documents Microsoft
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
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44dcc58aed4025af2e3e2177e978633c13f0ef20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="active-technology-and-dlls"></a>Technologie active et DLL
Technologie active permet de serveurs d’objets à mettre en œuvre entièrement à l’intérieur d’une DLL. Ce type de serveur est appelé serveur in-process. MFC ne gère pas complètement les serveurs in-process pour toutes les fonctionnalités d’édition, essentiellement parce que la technologie Active ne fournit pas un moyen pour un serveur de se connecter à la boucle de messages principale du conteneur. MFC requiert l’accès à la boucle de message de l’application conteneur pour gérer les touches d’accès et le traitement des temps d’inactivité.  
  
 Si vous écrivez un serveur Automation et que votre serveur ne dispose pas d’interface utilisateur, vous pouvez rendre votre serveur un serveur in-process et l’intégrer complètement dans une DLL.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
  
-   [Serveurs Automation](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>Voir aussi  
 [DLL dans Visual C++](../build/dlls-in-visual-cpp.md)