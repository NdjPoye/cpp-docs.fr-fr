---
title: "2.7 Data Environment | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7 Data Environment
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cette section présente une directive et plusieurs clauses pour contrôler l'environnement de données pendant l'exécution des régions parallèles, comme suit :  
  
-   Une directive de **threadprivate** \(consultez la section suivante\) est fournie pour effectuer la portée du fichier, la portée de l'espace de noms, ou les variables statiques de portée de bloc locales à un thread.  
  
-   Les clauses qui peuvent être spécifiées sur les directives pour contrôler les attributs de partage des variables pour la durée des éléments parallèles de partage du travail sont décrites dans [section 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) à la page 25.