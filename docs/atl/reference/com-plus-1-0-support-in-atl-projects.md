---
title: "Prise en charge COM+&#160;1.0 dans les projets ATL | Microsoft Docs"
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
  - "vc.appwiz.ATL.MTS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, prise en charge de COM+ 1.0"
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge COM+&#160;1.0 dans les projets ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'[Assistant Projet ATL](../../atl/reference/creating-an-atl-project.md) pour créer un objet offrant une prise en charge de base des composants COM\+ 1.0.  
  
 COM\+ 1.0 est conçu pour le développement d'applications distribuées utilisant des composants.  Il fournit également une infrastructure runtime pour le déploiement et la gestion de ces applications.  
  
 Si vous activez la case à cocher **Prendre en charge COM\+ 1.0**, l'Assistant modifie les liens définis dans le script de génération.  Le projet COM\+ 1.0 est lié aux bibliothèques spécifiques suivantes :  
  
-   comsvcs.lib  
  
-   Mtxguid.lib  
  
 Si vous activez la case à cocher **Prendre en charge COM\+ 1.0**, vous pouvez aussi activer **Prendre en charge l'inscription de composants**.  L'inscription de composants permet à votre objet COM\+ 1.0 d'obtenir une liste des composants, d'inscrire des composants ou d'annuler l'inscription de composants \(individuellement ou tous en même temps\).  
  
## Voir aussi  
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmation avec ATL et le code C Run\-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)