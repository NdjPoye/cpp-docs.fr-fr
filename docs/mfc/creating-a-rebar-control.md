---
title: "Cr&#233;ation d&#39;un contr&#244;le rebar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl (classe), créer"
  - "rebar (contrôles), créer"
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Cr&#233;ation d&#39;un contr&#244;le rebar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les objets [CReBarCtrl](../mfc/reference/crebarctrl-class.md) doivent être créés avant que l'objet parent soit visible.  Cela réduit les possibilités de problèmes de peinture.  
  
 Par exemple, les contrôles rebars \(utilisés dans les objets cadre de fenêtre\) sont fréquemment utilisés comme des fenêtres parentes pour les contrôles de la barre d'outils.  Par conséquent, le parent du contrôle rebar est l'objet cadre de fenêtre.  Comme l'objet cadre de fenêtre est le parent, la fonction membre de `OnCreate` \(du parent\) est un excellent emplacement pour créer le contrôle rebar.  
  
 Pour utiliser un objet `CReBarCtrl`, vous suivrez généralement les étapes suivantes :  
  
### Pour utiliser un objet de CReBarCtrl  
  
1.  Construisez l'objet [CReBarCtrl](../mfc/reference/crebarctrl-class.md).  
  
2.  Appelez [Créer](../Topic/CReBarCtrl::Create.md) pour créer le contrôle rebar commun Windows et le joindre à l'objet `CReBarCtrl`, en spécifiant les styles de votre choix.  
  
3.  Chargement d'une bitmap, par un appel à [CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md), pour être utilisé comme arrière\-plan de l'objet de contrôle rebar.  
  
4.  Créez et initialisez tous les objets de fenêtre enfant \(barres d'outils, contrôles de la boîte de dialogue, etc.\) qui sont contenus dans l'objet de contrôle rebar.  
  
5.  Initialise une structure de **REBARBANDINFO** avec les informations nécessaires pour la bande sur le point d'être insérée.  
  
6.  Appelez [InsertBand](../Topic/CReBarCtrl::InsertBand.md) pour insérer les fenêtres enfants existantes \(par exemple `m_wndReToolBar`\) dans le nouveau contrôle rebar.  Pour plus d'informations sur l'insertion de bandes dans un contrôle rebar existant, consultez [Contrôles rebars et bandes](../mfc/rebar-controls-and-bands.md).  
  
## Voir aussi  
 [Utilisation de CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)