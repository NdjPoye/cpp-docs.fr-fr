---
title: 4.4 OMP_NESTED | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fbb45bb04db612451c7d081f3a7afad8031da643
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
Le `OMP_NESTED` variable d’environnement Active ou désactive le parallélisme imbriqué, sauf si le parallélisme imbriquée est activée ou désactivée en appelant le `o` **mp_set_nested** routine de bibliothèque. Si la valeur **TRUE**, parallélisme imbriquée est activée ; si elle est définie sur **FALSE**imbriquée parallélisme est désactivé. La valeur par défaut est **FALSE**.  
  
 Exemple :  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>Référence croisée :  
  
-   `omp_set_nested`fonction, consultez [Section 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) page 40.