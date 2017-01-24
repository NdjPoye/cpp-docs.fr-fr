---
title: "Recommendations for Choosing Between ATL and MFC | Microsoft Docs"
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
helpviewer_keywords: 
  - "ATL, différences par rapport à MFC"
  - "MFC, ATL support"
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recommendations for Choosing Between ATL and MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous développez des composants et des applications, vous pouvez choisir entre deux approches \(ATL et MFC \(la bibliothèque MFC\).  
  
## Utilisation de ATL  
 ATL est un moyen rapide, la méthode simple pour créer un composant COM en C\+\+ et conservent un encombrement réduit.  Utilisez ATL pour créer un contrôle si vous n'avez pas besoin de toutes les fonctionnalités intégrées que MFC fournit automatiquement.  
  
## Utilisation de MFC  
 MFC vous permet de créer des applications complètes, les contrôles ActiveX, les documents actifs.  Si vous avez déjà créé un contrôle avec MFC, vous pouvez continuer le développement dans MFC.  En créant un contrôle, envisagez l'utilisation d'ATL si vous n'avez pas besoin de toutes les fonctionnalités intégrées MFC.  
  
## À l'aide de ATL dans un projet MFC  
 Vous pouvez ajouter la prise en charge d'utiliser ATL dans un projet MFC existant en exécutant un assistant.  Pour plus d'informations, consultez l' [ajouter la prise en charge ATL à votre projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
## Voir aussi  
 [Introduction to ATL](../atl/introduction-to-atl.md)