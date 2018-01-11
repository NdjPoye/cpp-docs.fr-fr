---
title: "2.7 environnement des données | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e018a2c1b20bef640852ced913dc90266e733c06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="27-data-environment"></a>2.7 Environnement des données
Cette section présente une directive et plusieurs clauses pour contrôler l’environnement de données pendant l’exécution de régions parallèles, comme suit :  
  
-   A **threadprivate** directive (voir la section suivante) est fournie pour portée de fichier, espace de noms de portée ou variables static de portée de bloc local à un thread.  
  
-   Les clauses qui peuvent être spécifiées sur les directives pour contrôler les attributs de partage des variables pour la durée des constructions parallèles ou partage de travail sont décrites dans [Section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) page 25.