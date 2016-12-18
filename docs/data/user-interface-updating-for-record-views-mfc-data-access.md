---
title: "Mise &#224; jour de l&#39;interface utilisateur pour les vues des enregistrements (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "menus, mettre à jour au fur et à mesure des changements de contexte"
  - "vues des enregistrements, interface utilisateur"
  - "interfaces utilisateur, mettre à jour"
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mise &#224; jour de l&#39;interface utilisateur pour les vues des enregistrements (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CRecordView` et `CDaoRecordView` fournissent également des gestionnaires de mise à jour de l'interface utilisateur par défaut pour les commandes de navigation.  Ces gestionnaires automatisent l'activation et la désactivation des objets d'interface utilisateur \(éléments de menu et boutons de barre d'outils\).  L'Assistant Application fournit des menus standard et, si vous choisissez l'option **Barre d'outils ancrable**, un ensemble de boutons de barre d'outils pour les commandes.  Si vous créez une classe de vue d'enregistrement à l'aide de `CRecordView`, vous pouvez ajouter des objets d'interface utilisateur similaires à votre application.  
  
### Pour créer des ressources de menu avec l'éditeur de menu  
  
1.  À l'aide des informations sur l'utilisation de l'[éditeur de menu](../mfc/menu-editor.md), créer votre propre menu avec ces quatre commandes.  
  
#### Pour créer des boutons de barre d'outils avec l'éditeur de graphismes  
  
1.  À l'aide des informations sur l'utilisation de l'[éditeur de barre d'outils](../mfc/toolbar-editor.md), modifiez la ressource de barre d'outils pour ajouter des boutons de barre d'outils pour vos commandes de navigation entre les enregistrements.  
  
## Voir aussi  
 [Prise en charge de la navigation dans une vue de l'enregistrement](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [Utilisation d'une vue de l'enregistrement](../data/using-a-record-view-mfc-data-access.md)