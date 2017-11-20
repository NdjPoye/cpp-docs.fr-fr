---
title: "Erreur irrécupérable C1026 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1026
dev_langs: C++
helpviewer_keywords: C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 187cfc1a59fc40a721be09aef9e78ef36c68f66a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1026"></a>Erreur irrécupérable C1026
dépassement de capacité de la pile de l'analyseur, programme trop complexe  
  
 L’espace requis pour analyser le programme a provoqué un dépassement de capacité de pile du compilateur.  
  
 Réduire la complexité des expressions en :  
  
-   Diminution du niveau d’imbrication des `for` et `switch` instructions. Placez les instructions plus profondément imbriquées dans des fonctions séparées.  
  
-   Avec rupture des expressions longues qui impliquent des appels de fonction ou des opérateurs de virgules.