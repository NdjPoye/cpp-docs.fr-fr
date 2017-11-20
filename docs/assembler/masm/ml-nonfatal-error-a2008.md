---
title: Erreur ML non fatale A2008 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2008
dev_langs: C++
helpviewer_keywords: A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7bcef41e81ea0f3d6229cf828a661fdc8f8fdec4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ml-nonfatal-error-a2008"></a>Erreur ML non fatale A2008
**Erreur de syntaxe :**  
  
 Un jeton à l’emplacement actuel a provoqué une erreur de syntaxe.  
  
 Une des opérations suivantes peut-être se sont produites :  
  
-   Un préfixe de point a été ajouté à ou omis à partir d’une directive.  
  
-   Un mot réservé (tel que **C** ou **taille**) a été utilisé en tant qu’identificateur.  
  
-   Une instruction a été utilisée qui n’était pas disponible avec la sélection actuelle de processeur ou de coprocesseur.  
  
-   Un opérateur d’exécution de comparaison (tels que `==`) a été utilisée dans une instruction conditionnelle assembly au lieu d’un opérateur relationnel (tel que [EQ](../../assembler/masm/operator-eq.md)).  
  
-   Une instruction ou une directive a été spécifiée trop peu d’opérandes.  
  
-   Une directive obsolète a été utilisée.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)