---
title: "Diff&#233;rences entre CReBar et CReBarCtrl | Microsoft Docs"
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
  - "CReBar"
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar (classe), différences par rapport à CReBarCtrl"
  - "GetReBarCtrl (classe)"
  - "rebar (contrôles), CReBarCtrl (classe)"
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Diff&#233;rences entre CReBar et CReBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit deux classes pour créer rebar : [CToolBar](../mfc/reference/crebar-class.md) et [CToolBarCtrl](../mfc/reference/crebarctrl-class.md) \(qui encapsule l'API de contrôle commun Windows\).  **CReBar** fournit toutes les fonctionnalités du contrôle rebar commun, et il gère plusieurs des paramètres et des structures nécessaires de contrôle commun pour vous.  
  
 `CReBarCtrl` est une classe wrapper pour le contrôle rebar Win32, et peut donc être plus facile à implémenter si vous n'envisagez pas l'intention d'intégrer la rebar dans l'architecture MFC.  Si vous envisagez d'utiliser `CReBarCtrl` et pour intégrer le rebar d'état dans l'architecture de MFC, vous devez prendre des précautions supplémentaires pour communiquer des manipulations de contrôle de rebar à MFC.  Cette communication n'est pas difficile ; toutefois, il s'agit d'un travail supplémentaire qui n'est pas nécessaire lorsque vous utilisez **CReBar**.  
  
 Visual C\+\+ propose deux manières de tirer parti du contrôle courant de rebar.  
  
-   Créez le rebar à **CReBar**, puis appelez [CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) pour obtenir l'accès aux fonctions membres `CReBarCtrl`.  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl` est une fonction membre intégrée qui caste le pointeur **this** de l'objet rebar.  Cela signifie que, pendant l'exécution, l'appel de fonction n'a aucune charge mémoire.  
  
-   Créez le rebar à l'aide du constructeur [CReBarCtrl](../mfc/reference/crebarctrl-class.md).  
  
 L'une ou l'autre méthode vous donnera l'accès aux fonctions membres à partir du contrôle rebar.  Lorsque vous appelez `CReBar::GetReBarCtrl`, il retourne une référence à un objet de `CReBarCtrl` donc vous pouvez utiliser l'un ou l'autre ensemble de fonctions de membre.  Voir [CReBar](../mfc/reference/crebar-class.md) pour plus d'informations sur la construction et la création d'un rebar en utilisant **CReBar**.  
  
## Voir aussi  
 [Utilisation de CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)