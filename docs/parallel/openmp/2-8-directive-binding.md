---
title: 2.8 liaison de directives | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 731c509c0c2f300d7a9d4e39261ffedd1c22a094
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="28-directive-binding"></a>2.8 Liaison de directives
Liaison dynamique des directives doit respecter les règles suivantes :  
  
-   Le **pour**, **sections**, **unique**, **master**, et **barrière** directives lier à la dynamique englobant **parallèles**, s’il en existe, quelle que soit la valeur de n’importe quel **si** clause pouvant être présent sur cette directive. Si aucune région parallèle n’est en cours d’exécution, les directives sont exécutées par une équipe composée d’uniquement sur le thread principal.  
  
-   Le **classés** la directive est liée à la dynamique englobante **pour**.  
  
-   Le **atomique** directive applique un accès exclusif au niveau **atomique** directives dans tous les threads, et pas seulement l’équipe actuelle.  
  
-   Le **critique** directive applique un accès exclusif au niveau **critique** directives dans tous les threads, et pas seulement l’équipe actuelle.  
  
-   Une directive ne peut jamais lier dynamiquement à aucune directive en dehors de la plus proche englobant **parallèles**.