---
title: "Cr&#233;ation d&#39;un conteneur de contr&#244;les ActiveX MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.activex.container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conteneurs de contrôles ActiveX (C++), créer"
  - "conteneurs (C++), créer"
  - "contrôles ActiveX MFC (C++), conteneurs"
  - "contrôles OLE (C++), conteneurs"
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un conteneur de contr&#244;les ActiveX MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un conteneur de contrôles ActiveX est un programme parent qui fournit l'environnement nécessaire à l'exécution d'un contrôle ActiveX \(appelé OLE auparavant\).  Vous pouvez créer une application capable de contenir des contrôles ActiveX avec ou sans l'aide de MFC, mais il est plus simple de le faire en utilisant MFC.  
  
 La création d'un programme conteneur MFC en utilisant l'[Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md) vous permet d'accéder aux principales fonctionnalités des contrôles ActiveX et Automation qui sont implémentées par les classes MFC et ActiveX.  Ces fonctionnalités comprennent l'édition visuelle, l'Automation, la création de fichiers composés et la prise en charge des contrôles.  Les options d'édition visuelle de l'Assistant Application MFC que prend en charge votre programme parent comprennent la création d'un conteneur, d'un mini serveur, d'un serveur complet et un programme qui sert à la fois de conteneur et de serveur.  
  
-   **Nouvelle application MFC**.  Pour créer un nouveau programme MFC contenant Automation, l'édition visuelle, les fichiers composés ou la prise en charge du contrôle, utilisez l'Assistant Application MFC et choisissez les options Automation appropriées.  
  
-   **Application MFC existante**.  Si vous ajoutez la prise en charge de la relation contenant\-contenu de contrôles à une application MFC existante, consultez [Conteneurs de contrôles OLE : activation manuelle de la contenance de contrôles OLE](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).  
  
### Pour créer un conteneur ActiveX pour l'un des types d'applications suivants :  
  
1.  [Conteneurs](../../mfc/containers.md)  
  
2.  [Édition visuelle](../../mfc/ole-mfc.md)  
  
3.  [Contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md)  
  
## Voir aussi  
 [Types de projets Visual C\+\+](../../ide/visual-cpp-project-types.md)