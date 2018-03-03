---
title: -LINKERMEMBER | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /linkermember
dev_langs:
- C++
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86248b226f40da62282d7a8fb4f5847e6e617915
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linkermember"></a>/LINKERMEMBER
```  
/LINKERMEMBER[:{1|2}]  
```  
  
## <a name="remarks"></a>Notes  
 Cette option affiche les symboles publics définis dans une bibliothèque. Spécifiez le 1 argument pour afficher les symboles dans l’ordre de l’objet, ainsi que leurs offsets. Spécifier l’argument 2 pour afficher les offsets et les numéros d’index des objets et répertorie ensuite les symboles dans l’ordre alphabétique, ainsi que l’index de l’objet pour chacun. Pour obtenir les deux sorties, spécifiez /LINKERMEMBER dans l’argument de nombre.  
  
 Uniquement les [/HEADERS](../../build/reference/headers.md) (option DUMPBIN) est disponible pour les fichiers générés par le [/GL](../../build/reference/gl-whole-program-optimization.md) option du compilateur.  
  
## <a name="see-also"></a>Voir aussi  
 [DUMPBIN, options](../../build/reference/dumpbin-options.md)