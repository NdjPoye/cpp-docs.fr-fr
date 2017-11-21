---
title: "1.1 étendue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b4f348f55cb956802bab9651b22804c941c53cdb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="11-scope"></a>1.1 Portée
Cette spécification couvre la parallélisation uniquement dirigées par l’utilisateur, dans laquelle l’utilisateur spécifie explicitement les actions à entreprendre par le compilateur et le système d’exécution afin d’exécuter le programme en parallèle. Implémentations OpenMP C et C++ ne sont pas requis pour rechercher les dépendances, est en conflit, des interblocages, des conditions de concurrence ou autres problèmes qui résultent de l’exécution du programme incorrect. L’utilisateur est chargé de s’assurer que l’application en utilisant les constructions OpenMP C et C++ API s’exécute correctement. La parallélisation automatique généré par le compilateur et les directives du compilateur pour faciliter ce type parallélisation ne sont pas traités dans ce document.