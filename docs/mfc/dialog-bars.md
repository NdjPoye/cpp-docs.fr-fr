---
title: "Barres de bo&#238;te de dialogue | Microsoft Docs"
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
  - "CDialogBar (classe), barres de boîte de dialogue"
  - "barres de contrôles, barres de boîte de dialogue"
  - "barres de boîte de dialogue"
  - "barres de boîte de dialogue, à propos des barres de boîte de dialogue"
  - "MFC, barres de contrôles"
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Barres de bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une barre de dialogue est une barre d'outils, un type de [barre de contrôle](../mfc/control-bars.md) qui peut contenir n'importe quel type de contrôle.  Étant donné qu'il possède les caractéristiques d'une boîte de dialogue non modale, un objet [CDialogBar](../mfc/reference/cdialogbar-class.md) fournit une barre d'outils plus puissante.  
  
 Il existe plusieurs différences majeures entre une barre d'outils et un objet `CDialogBar`.  Un objet `CDialogBar` est créé à partir d'une ressource modèle de dialogue, que vous pouvez créer à l'aide de Visual C\+\+ l'éditeur de dialogue Visual C\+\+ et qui peut contenir n'importe quel type de contrôle Windows.  L'utilisateur peut utiliser les touches de tabulation pour passer de contrôle en contrôle.  Vous pouvez spécifier un style d'alignement pour aligner la barre de de dialogue avec n'importe quelle partie de la fenêtre parente ou même la laisser en place si le parent est redimensionné.  L'illustration suivante montre une barre de dialogue avec différents types de contrôles.  
  
 ![Barre de boîte de dialogue VC](../mfc/media/vc378t1.png "vc378T1")  
Une barre de dialogue  
  
 A d'autres égards, l'utilisation d'un objet `CDialogBar` revient à utiliser une boîte de dialogue non modale.  Utilisez l'éditeur de dialogues pour concevoir et créer la ressource de dialogue.  
  
 Une des vertus des barres de dialogue est qu'elles peuvent inclure des contrôles autres que les boutons.  
  
 Même s'il est normal partir de vos propres classes de dialogue de `CDialog`, vous dérivez ne pas généralement votre propre classe pour une barre de dialogue.  Les barres de dialogue sont des extensions d'une fenêtre principale et tous les messages de notification de contrôle de la barre de dialogue, tels que **BN\_CLICKED** ou **EN\_CHANGE**, sont envoyés au parent de la barre de dialogue, la fenêtre principale.  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)   
 [Exemple](../top/visual-cpp-samples.md)