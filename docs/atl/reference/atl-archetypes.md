---
title: "ATL Archetypes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "archetype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, archetypes"
ms.assetid: 809fb0af-c0f4-4cc0-b5bc-afe3de5d9722
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Archetypes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans ce contexte, *un archétype* est une classe conceptuelle qui fournit une collection de méthodes, des données membres, fonctions static, typedefs, ou autre la comporte.  L'archétype inclut également une description de la sémantique nécessaire pour créer ou utiliser la classe pour représenter un concept particulier.  Les classes qui reproduisent l'archétype en fournissant les fonctionnalités incarnent le même concept et peuvent être utilisées où l'archétype peuvent être utilisées.  
  
 Les archétypes sont utiles en C\+\+ pour décrire les fonctionnalités des valeurs valides pour les paramètres de modèle.  Le concepteur du modèle a une idée claire des fonctionnalités nécessaires et suffisantes du paramètre de modèle, le compilateur imposera les exigences syntaxiques au moment de la génération, mais l'utilisateur d'un modèle a besoin de documentation pour décrire la sémantique et autoriser les relations entre les archétypes et les classes à définir clairement.  
  
 Les exemples de archétypes dans la bibliothèque C\+\+ standard sont les différents types de l'itérateur et du conteneur.  Ces archétypes sont décrits dans les rubriques [conventions d'itérateur](../../standard-library/iterators.md) et [Conteneurs STL](../../standard-library/stl-containers.md).  
  
 ATL Server définit les archétypes suivants :  
  
|Nom|Description|  
|---------|-----------------|  
|[Archétype de travail](../../atl/reference/worker-archetype.md)|Les classes conformes à l'archétype *de travail* fournissent le code aux éléments de travail par processus mis en file d'attente sur un pool de threads.|  
  
## Voir aussi  
 [Concepts](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)