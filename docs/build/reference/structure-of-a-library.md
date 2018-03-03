---
title: "Structure d’une bibliothèque | Documents Microsoft"
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
- libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1630636b0de552712f67bc43b5182f991b10ef0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="structure-of-a-library"></a>Structure d'une bibliothèque
Une bibliothèque contient des objets COFF. Les objets dans une bibliothèque de contenir des fonctions et des données qui peuvent être référencées en externe par d’autres objets dans un programme. Un objet dans une bibliothèque est parfois appelée un membre de bibliothèque.  
  
 Vous pouvez obtenir des informations supplémentaires sur le contenu d’une bibliothèque en exécutant l’outil DUMPBIN avec l’option /LINKERMEMBER. Pour plus d’informations sur cette option, consultez [Référence DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de LIB](../../build/reference/overview-of-lib.md)