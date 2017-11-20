---
title: "Déduit des règles et dépendants | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 68b61a6aad55ef1f6b8b5807d857a4d7239ebb51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="inferred-dependents-and-rules"></a>Règles et dépendants inférés
NMAKE suppose un dépendant déduit pour une cible si une règle d’inférence applicable existe. Une règle s’applique si :  
  
-   *toext* correspond à extension de la cible.  
  
-   *fromext* correspond à l’extension d’un fichier qui a le nom de base de la cible et qui existe dans le répertoire actuel ou spécifié.  
  
-   *fromext* est [. SUFFIXES](../build/dot-directives.md); aucun autre *fromext* dans une règle de correspondance a un degré plus élevé **. SUFFIXES** priorité.  
  
-   Aucun dépendant explicite n’est plus élevé **. SUFFIXES** priorité.  
  
 Dépendants inférés peuvent avoir des effets secondaires inattendus. Si le bloc de description de la cible contient des commandes, NMAKE exécute les commandes au lieu des commandes dans la règle.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles d’inférence](../build/inference-rules.md)