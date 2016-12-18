---
title: "Proc&#233;dure de fen&#234;tre, points d&#39;entr&#233;e | Microsoft Docs"
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
  - "points d'entrée, procédures de fenêtre"
  - "MFC, gérer des données d'état"
  - "gestion d'état, procédures de fenêtre"
  - "procédure de fenêtre (points d'entrée)"
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure de fen&#234;tre, points d&#39;entr&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour protéger les procédures de MFC, une ligne statique de module crée une liaison avec une implémentation de la procédure spéciale de fenêtre.  La liaison se produit automatiquement lorsque le module est lié à MFC.  Cette procédure d'affichage utilise la macro de `AFX_MANAGE_STATE` pour définir correctement l'état du module efficace, puis il appelle **AfxWndProc**, qui délègue ensuite à `WindowProc` la fonction membre de `CWnd`approprié \- objet dérivé.  
  
## Voir aussi  
 [Gestion des données d'état des modules MFC](../mfc/managing-the-state-data-of-mfc-modules.md)