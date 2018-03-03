---
title: "Erreur irrécupérable C1307 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe97f1658a74b0db5985ed755bf387811f2c6d1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1307"></a>Erreur irrécupérable C1307
le programme a été modifié depuis que les données du profil ont été recueillies  
  
 Lorsque vous utilisez [/LTCG : PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), l’éditeur de liens a détecté un module d’entrée qui a été recompilé après/LTCG : PGINSTRUMENT et que le module a été modifié au point où les données de profil existante ne soient plus pertinentes. Par exemple, si le graphique des appels a changé dans le module recompilé, le compilateur générera C1307.  
  
 Pour résoudre cette erreur, exécutez/LTCG : PGINSTRUMENT, restauration par progression de toutes les séries de tests et exécutez/LTCG : PGOPTIMIZE. Si vous ne pouvez pas exécuter/LTCG : PGINSTRUMENT et restauration par progression de que tous les tests s’exécute, utilisez/LTCG : PGUPDATE au lieu de/LTCG : PGOPTIMIZE pour créer l’image optimisée.