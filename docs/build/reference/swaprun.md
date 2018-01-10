---
title: -SWAPRUN | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /swaprun
dev_langs: C++
helpviewer_keywords:
- /SWAPRUN editbin option
- -SWAPRUN editbin option
- SWAPRUN editbin option
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 249ed999d9a60116875e88553863ef5cd234ade9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="swaprun"></a>/SWAPRUN
```  
/SWAPRUN:{[!]NET|[!]CD}  
```  
  
## <a name="remarks"></a>Notes  
 Cette option modifie l’image pour indiquer au système d’exploitation pour copier l’image dans un fichier d’échange et exécutez-le à partir de là. Utilisez cette option pour les images qui résident sur des réseaux ou un support amovible.  
  
 Vous pouvez ajouter ou supprimer les qualificateurs NET ou CD :  
  
-   NET indique que l’image réside sur un réseau.  
  
-   CD indique que l’image se trouve sur un CD-ROM ou un support amovible similaire.  
  
-   Utilisez ! NET et ! CD pour inverser les effets de NET et CD.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)