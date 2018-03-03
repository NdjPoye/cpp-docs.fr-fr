---
title: "Évaluateur d’expression, erreur CXX0015 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6f671b39fcc0027fdad5308192c5cbd8b8973717
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0015"></a>Évaluateur d'expression, erreur CXX0015
expression trop complexe (dépassement de capacité de pile)  
  
 L’expression est trop complexe ou imbriquées trop profondément pour la quantité de stockage disponible pour l’évaluateur d’expression C.  
  
 Dépassement de capacité se produit généralement en raison du trop grand nombre de calculs en attente.  
  
 Réorganiser l’expression afin que chaque composant de l’expression peut être évaluée, tel qu’il est trouvé, au lieu de devoir attendre d’autres parties de l’expression doit être calculée.  
  
 Fractionnez l’expression en plusieurs commandes.  
  
 Cette erreur est identique à CAN0015.