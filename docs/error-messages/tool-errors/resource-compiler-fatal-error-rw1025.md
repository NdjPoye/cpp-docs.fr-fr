---
title: "Erreur irrécupérable RW1025 du compilateur de ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 487968f8a1242dd4c36e4bbd9b4ede08a5ab4d95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Erreur irrécupérable RW1025 du compilateur de ressources 
La mémoire de tas lointain  
  
 Rechercher les logiciels de résidant en mémoire qui peut occuper trop d’espace. Le programme CHKDSK permet de déterminer la quantité de mémoire.  
  
 Si vous créez un fichier de ressources volumineux, fractionner le script de ressources en deux fichiers. Après avoir créé les deux fichiers .res, utilisez la ligne de commande MS-DOS pour joindre les :  
  
```  
copy first.res /b + second.res /b full.res  
```