---
title: "Avertissement LNK4022 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e35974a72de349f94f2189f676b6dc955c48fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4022"></a>Avertissement des outils Éditeur de liens LNK4022
Impossible de trouver une correspondance unique pour le symbole 'symbole'  
  
 LINK ou LIB a trouvé plusieurs correspondances pour le symbole non décoré donné et ne peut pas résoudre l’ambiguïté. Aucun fichier de sortie (.exe, .dll, .exp ou .lib) n’est généré. Cet avertissement est suivi par un avertissement [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) pour chaque dupliquer le symbole et finalement suivi de l’erreur irrécupérable [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Pour éviter cet avertissement, spécifiez le symbole dans sa forme décorée. Exécutez [DUMPBIN](../../build/reference/dumpbin-options.md) sur l’objet pour voir les noms décorés.