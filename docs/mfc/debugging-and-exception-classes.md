---
title: "Débogage et Classes d’Exception | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.debug
dev_langs: C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 622e6d04a567668ebfd2c737c5cdde1c2ea09b35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="debugging-and-exception-classes"></a>Débogage et classes d'exceptions
Ces classes fournissent la prise en charge pour le débogage d’allocation de mémoire dynamique, ainsi que pour passer des informations sur les exceptions à partir de la fonction où l’exception est levée à la fonction dans laquelle elle est interceptée.  
  
 Utilisez les classes [CDumpContext](../mfc/reference/cdumpcontext-class.md) et [CMemoryState](../mfc/reference/cmemorystate-structure.md) lors du développement afin de faciliter le débogage, comme décrit dans [débogage des Applications MFC](/visualstudio/debugger/mfc-debugging-techniques). Utilisez [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) pour déterminer la classe de n’importe quel objet en cours d’exécution, comme décrit dans l’article [l’accès aux informations de classe d’exécution](../mfc/accessing-run-time-class-information.md). L’infrastructure utilise `CRuntimeClass` pour créer dynamiquement des objets d’une classe particulière.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

