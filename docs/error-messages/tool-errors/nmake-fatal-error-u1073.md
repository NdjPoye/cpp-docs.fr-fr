---
title: "Erreur irrécupérable NMAKE U1073 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faae317df44560991a88d47ec7f123e6a8126429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1073"></a>Erreur irrécupérable NMAKE U1073
incapable de rendre 'targetname'  
  
 La cible spécifiée n’existe pas, et aucune commande à exécuter ou d’une règle d’inférence à appliquer.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Vérifiez l’orthographe du nom de la cible.  
  
2.  Si *targetname* est une pseudocible, spécifiez-la en tant que cible dans un autre bloc de description.  
  
3.  Si *targetname* est un appel de macro, veillez à ne développe pas une chaîne null.