---
title: "D&#233;finition de gestionnaires d&#39;&#233;v&#233;nements pour les contr&#244;les ActiveX | Microsoft Docs"
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
  - "contrôles ActiveX (C++), événements"
  - "événements (C++), contrôles ActiveX"
ms.assetid: c076386f-c78b-4dc9-9201-a544252d5337
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition de gestionnaires d&#39;&#233;v&#233;nements pour les contr&#244;les ActiveX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les contrôles ActiveX peuvent être programmés de façon à réagir aux événements.  Vous pouvez appliquer **ControlEvents** aux propriétés afin de connaître les événements qui sont disponibles dans un contrôle et créer des gestionnaires d'événements.  La gestion d'événements est couramment utilisée afin d'intercepter les modifications dans la requête de la source de données.  Les modifications sont les suivantes :  
  
-   Implémentation d'une recherche.  Quand un contrôle \(une zone DBCombo, par exemple\) change de valeur, l'événement de changement est intercepté afin de mettre à jour la requête d'un contrôle de données.  
  
-   Implémentation d'une relation Maître\/Détail.  Deux contrôles de données sont ajoutés à une boîte de dialogue, le premier pour la partie maître et le second pour la partie détail.  Chaque fois que la première source de données est modifiée, la requête de la seconde source de données est mise à jour via un gestionnaire d'événements.  
  
-   Interception des erreurs.  La plupart des contrôles possèdent un événement d'erreur à partir duquel vous pouvez écrire un gestionnaire d'erreurs \(consultez [Interception des erreurs](../../data/ado-rdo/error-trapping.md)\).  
  
 Pour plus d'informations, consultez [Mappage de messages en fonctions](../../mfc/reference/mapping-messages-to-functions.md).  
  
## Voir aussi  
 [Utilisation des contrôles ActiveX](../../data/ado-rdo/using-activex-controls.md)