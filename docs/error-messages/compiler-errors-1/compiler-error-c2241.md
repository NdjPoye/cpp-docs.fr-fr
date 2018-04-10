---
title: Erreur du compilateur C2241 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C2241
dev_langs:
- C++
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7bbd320e93150d163db78f4fd089c319d30cbfd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2241"></a>Erreur du compilateur C2241
'identifier' : accès au membre restreint  
  
 Le code tente d’accéder à un membre privé ou protégé.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Modifiez le niveau d’accès du membre.  
  
2.  Déclarez le membre comme `friend` de la fonction qui y accède.