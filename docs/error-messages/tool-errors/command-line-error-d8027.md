---
title: Erreur de ligne de commande D8027 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1bd66688dbf582bf38fb9a0a3706663db3cf145d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-error-d8027"></a>Erreur de ligne de commande D8027
Impossible d’exécuter 'composant'  
  
 Le compilateur n’a pas pu exécuter le composant de donnée du compilateur ou l’éditeur de liens.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Mémoire insuffisante pour charger le composant. Si NMAKE a appelé le compilateur, exécutez le compilateur en dehors du makefile.  
  
2.  Le système d’exploitation actuel n’a pas pu exécuter le composant. Assurez-vous que le chemin pointe vers les fichiers exécutables correspondant à votre système d’exploitation.  
  
3.  Le composant a été endommagé. Recopiez le composant à partir de disques de distribution, à l’aide du programme d’installation.  
  
4.  Une option a été spécifiée correctement. Exemple :  
  
    ```  
    cl /B1 file1.c  
    ```