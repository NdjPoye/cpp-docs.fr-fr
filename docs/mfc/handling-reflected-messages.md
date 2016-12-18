---
title: "Gestion des messages r&#233;fl&#233;chis | Microsoft Docs"
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
  - "gestion des messages, messages réfléchis"
  - "messages réfléchis, gérer"
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des messages r&#233;fl&#233;chis
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le renvoi de message vous permet de gérer des messages pour un contrôle, tels que `WM_CTLCOLOR`, **WM\_COMMAND**, et **WM\_NOTIFY**, dans le contrôle lui\-même.  Cela rend le contrôle plus autonome et portable.  Le mécanisme utilise des contrôles communs de Windows ainsi que des contrôles ActiveX \(anciennement appelé contrôles OLE\).  
  
 Le renvoi de message vous permet de réutiliser vos classes dérivées de `CWnd`plus facilement.  Le renvoi de message fonctionne via [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md), à l'aide d'entrées spéciales de la map de messages **ON\_XXX\_REFLECT** : par exemple, **ON\_CTLCOLOR\_REFLECT** et **ON\_CONTROL\_REFLECT**.  [Note technique 62](../mfc/tn062-message-reflection-for-windows-controls.md) décrit le renvoi de message plus en détail.  
  
## Que voulez\-vous faire ?  
  
-   [En savoir plus sur le renvoi de message](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implémentez le renvoi de message pour un contrôle commun](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implémentez le renvoi de message pour un contrôle ActiveX](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## Voir aussi  
 [Déclaration des fonctions de gestionnaire de messages](../mfc/declaring-message-handler-functions.md)