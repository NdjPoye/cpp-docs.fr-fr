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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1173f538f02e8178d523bb51476b4a10427099ea
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1307"></a>Erreur irrécupérable C1307
le programme a été modifié depuis que les données du profil ont été recueillies  
  
 Lorsque vous utilisez [/LTCG : PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), l’éditeur de liens a détecté un module d’entrée qui a été recompilé après/LTCG : PGINSTRUMENT et que le module a été modifié au point où les données de profil existante ne soient plus pertinentes. Par exemple, si le graphique des appels a changé dans le module recompilé, le compilateur générera C1307.  
  
 Pour résoudre cette erreur, exécutez/LTCG : PGINSTRUMENT, restauration par progression de toutes les séries de tests et exécutez/LTCG : PGOPTIMIZE. Si vous ne pouvez pas exécuter/LTCG : PGINSTRUMENT et restauration par progression de que tous les tests s’exécute, utilisez/LTCG : PGUPDATE au lieu de/LTCG : PGOPTIMIZE pour créer l’image optimisée.
