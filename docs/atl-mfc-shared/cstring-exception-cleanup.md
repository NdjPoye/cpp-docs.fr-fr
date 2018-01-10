---
title: Nettoyage des exceptions CString | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 496fdfe6a609bd4eceae225c2568c915d38aef07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-exception-cleanup"></a>Nettoyage des exceptions CString
Dans les versions précédentes de MFC, il était important d’éliminer les [CString](../atl-mfc-shared/reference/cstringt-class.md) objets après utilisation. Avec MFC version 3.0 et versions ultérieure, un nettoyage explicite n’est plus nécessaire.  
  
 Sous l’exception C++ mécanisme MFC utilise désormais de gestion, il est inutile à vous soucier de nettoyage après une exception. Pour obtenir une description de la manière C++ « déroule » la pile après une exception est interceptée, consultez [try, catch et throw instructions](../cpp/try-throw-and-catch-statements-cpp.md). Même si vous utilisez la bibliothèque MFC **essayez**/**CATCH** macros au lieu des mots clés C++ **essayez** et **catch**, MFC utilise C++ mécanisme d’exception sous, donc vous toujours n’avez pas besoin nettoyer explicitement.  
  
## <a name="see-also"></a>Voir aussi  
 [Chaînes (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)

