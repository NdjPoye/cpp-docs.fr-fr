---
title: "Contr&#244;les ActiveX MFC&#160;: propri&#233;t&#233;s | Microsoft Docs"
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
  - "contrôles ActiveX MFC, propriétés"
  - "propriétés (MFC)"
  - "propriétés (MFC), contrôles ActiveX"
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: propri&#233;t&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle ActiveX lance des événements pour communiquer avec son conteneur de contrôle.  Le conteneur, en retour, utilise des methodes et des propriétés pour communiquer avec le contrôle.  Les méthodes et les propriétés sont similaires en usage et en but,respectivement, à des fonctions membres et à des variables membres d'une classe C\+\+.  Les propriétés sont des données membres du contrôle ActiveX qui sont exposées à tous les conteneurs.  Les propriétés fournissent une interface pour les applications qui contiennent des contrôlent ActiveX, telles que les clients Automation et les conteneurs de contrôle ActiveX.  
  
 Les propriétés sont également appelées des attributs.  
  
 Pour plus d'information sur les méthodes de contrôle ActiveX, voyez l'article [Contrôle MFC ActiveX : Méthodes](../mfc/mfc-activex-controls-methods.md).  
  
 Les contrôles ActiveX peuvent implémenter à la fois les méthodes personnalisées et de stockage et les propriétés.  La classe `COleControl` fournit une implémentation pour les propriétés de stock. \(Pour une liste complète des propriétés de stock, voir l'article [Contrôles MFC ActiveX: Ajouter des Propriétés de Stock](../mfc/mfc-activex-controls-adding-stock-properties.md).\) Les propriétés personnalisées, définies par le développeur, ajoutent des capacités spécialisées à un contrôle ActiveX.  Pour plus d'information, voyez [Contrôles MFC ActiveX : Ajout de Propriétés Personnalisées](../mfc/mfc-activex-controls-adding-custom-properties.md).  
  
 Les propriétés de stock et personnalisées, comme les méthodes, sont toutes deux supportées par un mecanisme qui consiste en une carte d'envois qui gère les propriétés et les méthodes ainsi que les fonctions membres de la classe `COleControl` existantes.  De plus, ces propriétés peuvent avoir des paramètres que le développeur utilise pour passer de l'information supplémentaire au contrôle.  
  
 L'article suivant discutent des propriétés de contrôle ActiveX en plus de détails:  
  
-   [Contrôles MFC ActiveX : Ajouter des Propriétés de Stock](../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Contrôles MFC ActiveX: Ajout de Propriétés Personnalisées](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Contrôles MFC ActiveX: Implémentation Avancée de Propriétés](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [Contrôles MFC ActiveX: Accès aux Propriétés Ambiantes](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)