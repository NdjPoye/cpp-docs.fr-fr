---
title: "Évaluateur d’expression, erreur CXX0015 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0015
dev_langs: C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6b04fd2b13b2acd9021dcd8e751a0b4cbefd166
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0015"></a>Évaluateur d'expression, erreur CXX0015
expression trop complexe (dépassement de capacité de pile)  
  
 L’expression est trop complexe ou imbriquées trop profondément pour la quantité de stockage disponible pour l’évaluateur d’expression C.  
  
 Dépassement de capacité se produit généralement en raison du trop grand nombre de calculs en attente.  
  
 Réorganiser l’expression afin que chaque composant de l’expression peut être évaluée, tel qu’il est trouvé, au lieu de devoir attendre d’autres parties de l’expression doit être calculée.  
  
 Fractionnez l’expression en plusieurs commandes.  
  
 Cette erreur est identique à CAN0015.