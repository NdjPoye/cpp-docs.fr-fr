---
title: Gestion des erreurs et Notification | Documents Microsoft
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
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 738721eb3fc37ba076157129cb88a22f2c90e464
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="error-handling-and-notification"></a>Gestion et notification des erreurs
Pour plus d’informations sur la gestion des erreurs et la notification, consultez [présentation de la fonction d’assistance](understanding-the-helper-function.md).  
  
 Pour plus d’informations sur les fonctions de raccordement, consultez [définitions des structures et constantes](../../build/reference/structure-and-constant-definitions.md).  
  
 Si votre programme utilise la DLL à chargement différé, il doit gérer efficacement les erreurs dans la mesure où les défaillances qui se produisent pendant l’exécution du programme provoquent des exceptions non gérées. Gestion de défaillance est composée de deux parties :  
  
 Récupération par un raccordement.  
 Si votre code doit récupérer ou fournir une autre bibliothèque et/ou la routine en cas d’échec, un raccordement peut être fourni à la fonction d’assistance qui peut fournir ou résoudre cette situation. La routine de raccordement doit retourner une valeur appropriée, afin que le traitement peut continuer (HINSTANCE ou FARPROC) ou 0 pour indiquer qu’une exception doit être levée. Elle peut également générer sa propre exception ou **longjmp** hors du hook. Des raccordements de notification et des raccordements de défaillance.  
  
 Création de rapports via une exception.  
 Si tout ce qui est nécessaire pour la gestion de l’erreur consiste à annuler la procédure, aucun raccordement n’est nécessaire tant que le code utilisateur peut gérer l’exception.  
  
 Les rubriques suivantes abordent la notification et la gestion des erreurs :  
  
-   [Raccordements de notification](../../build/reference/notification-hooks.md)  
  
-   [Raccordements de défaillance](../../build/reference/failure-hooks.md)  
  
-   [Exceptions](../../build/reference/exceptions-c-cpp.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de l’éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)