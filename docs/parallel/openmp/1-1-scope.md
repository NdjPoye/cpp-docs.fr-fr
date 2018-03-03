---
title: "1.1 étendue | Documents Microsoft"
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
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07859a95b739cf649ab6516cb2e8b605efe442dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="11-scope"></a>1.1 Portée
Cette spécification couvre la parallélisation uniquement dirigées par l’utilisateur, dans laquelle l’utilisateur spécifie explicitement les actions à entreprendre par le compilateur et le système d’exécution afin d’exécuter le programme en parallèle. Implémentations OpenMP C et C++ ne sont pas requis pour rechercher les dépendances, est en conflit, des interblocages, des conditions de concurrence ou autres problèmes qui résultent de l’exécution du programme incorrect. L’utilisateur est chargé de s’assurer que l’application en utilisant les constructions OpenMP C et C++ API s’exécute correctement. La parallélisation automatique généré par le compilateur et les directives du compilateur pour faciliter ce type parallélisation ne sont pas traités dans ce document.