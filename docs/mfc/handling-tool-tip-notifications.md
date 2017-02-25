---
title: "Gestion des notifications pour les info-bulles | Microsoft Docs"
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
  - "CToolBarCtrl (classe), gérer les notifications"
  - "notifications, info-bulles"
  - "info-bulles (C++), notifications"
  - "TOOLTIPTEXT (structure)"
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Gestion des notifications pour les info-bulles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous spécifiez le style de `TBSTYLE_TOOLTIPS`, la barre d'outils crée et gère un contrôle d'info\-bulle.  Une info\-bulle est une petite fenêtre indépendante qui contient une ligne de texte qui décrit un bouton de la barre d'outils.  L'info\-bulle est masquée, apparaissant uniquement lorsque l'utilisateur place le curseur sur un bouton de la barre d'outils et les feuilles durant environ une moitié de seconde.  L'info\-bulle apparaît à côté du curseur.  
  
 Avant que l'info\-bulle s'affiche, le message de notification **TTN\_NEEDTEXT** est envoyé à la fenêtre propriétaire de la barre d'outils afin de récupérer le texte descriptif pour le bouton.  Si la fenêtre propriétaire de la barre d'outils est une fenêtre de `CFrameWnd`, les info\-bulles apparaissent sans autre effort supplémentaire, car `CFrameWnd` possède un gestionnaire par défaut pour la notification de **TTN\_NEEDTEXT**.  Si la fenêtre propriétaire de la barre d'outils n'est pas dérivée de `CFrameWnd`, telle qu'une boîte de dialogue ou un mode formulaire, vous devez ajouter une entrée à la table des messages de la fenêtre propriétaire et fournir un gestionnaire de notification dans la table des messages.  L'entrée à la table des messages de la fenêtre propriétaire est la suivante :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/CPP/handling-tool-tip-notifications_1.cpp)]  
  
## Notes  
 `memberFxn`  
 La fonction membre à appeler lorsque le texte est nécessaire pour ce bouton.  
  
 Notez que l'ID d'une info\-bulle est toujours à 0.  
  
 Outre la notification de **TTN\_NEEDTEXT**, un contrôle d'info\-bulle peut envoyer les notifications suivantes à un contrôle de la barre d'outils:  
  
|Notification|Signification|  
|------------------|-------------------|  
|**TTN\_NEEDTEXTA**|Le contrôle d'info\-bulle pour le texte ASCII \(Windows 95 uniquement\)|  
|**TTN\_NEEDTEXTW**|Le contrôle d'info\-bulle pour le texte UNICODE \(Windows NT uniquement\)|  
|**TBN\_HOTITEMCHANGE**|Indique que l'élément \(en surbrillance\) a changé.|  
|**NM\_RCLICK**|Indique que l'utilisateur a cliqué avec le bouton droit sur un bouton.|  
|**TBN\_DRAGOUT**|Indique que l'utilisateur a cliqué sur le bouton et a fait glisser le pointeur hors du bouton.  Il permet à une application d'implémenter le glisser\-lâcher d'un bouton de la barre d'outils.  Lorsqu'elle reçoit cette notification, l'application démarre l'opération de glisser\-déplacer.|  
|**TBN\_DROPDOWN**|Indique que l'utilisateur a cliqué un bouton qui utilise le style de **TBSTYLE\_DROPDOWN**.|  
|**TBN\_GETOBJECT**|Indique que l'utilisateur a déplacé le pointeur sur un bouton qui utilise le style de **TBSTYLE\_DROPPABLE**.|  
  
 Pour obtenir un exemple la fonction gestionnaire et plus d'informations sur l'activation des info\-bulles, consultez [Info\-bulles](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)