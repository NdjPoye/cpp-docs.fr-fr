---
title: "Traitement des messages de notification dans un contr&#244;le rebar | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CReBarCtrl (classe), messages de notification envoyés par"
  - "notifications, CReBarCtrl"
  - "RBN_ (messages de notification)"
  - "RBN_ (messages de notification), description"
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement des messages de notification dans un contr&#244;le rebar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la classe parente du contrôle rebar, créez une fonction gestionnaire `OnChildNotify` avec une instruction switch pour tous les messages de notification de contrôle rebar \(`CReBarCtrl`\) à traiter.  Les notifications sont envoyées à la fenêtre parente lorsque l'utilisateur fait glisser des objets sur le contrôle rebar, modifie la disposition des bandes rebars, supprime les bandes du contrôle rebar, et ainsi de suite.  
  
 Les messages suivants de notification peuvent être envoyés par l'objet de contrôle rebar :  
  
-   **RBN\_AUTOSIZE** Envoyé par un contrôle rebar \(avec le style **RBS\_AUTOSIZE** \) lorsque le rebar se redimensionne automatiquement.  
  
-   **RBN\_BEGINDRAG** Envoyé par un contrôle rebar lorsque l'utilisateur commence à faire glisser une bande.  
  
-   **RBN\_CHILDSIZE** Envoyé par un contrôle rebar lorsque la fenêtre enfant d'une bande est redimensionnée.  
  
-   **RBN\_DELETEDBAND** Envoyé par un contrôle rebar lorsqu'une bande a été supprimée.  
  
-   **RBN\_DELETINGBAND** Envoyé par un contrôle rebar lorsqu'une bande va être supprimée.  
  
-   **RBN\_ENDDRAG** Envoyé par un contrôle rebar lorsque l'utilisateur arrête de faire glisser une bande.  
  
-   **RBN\_GETOBJECT** Envoyé par un contrôle rebar \(avec le style **RBS\_REGISTERDROP** \) lorsqu'un objet est déplacé sur une bande dans le contrôle.  
  
-   **RBN\_HEIGHTCHANGE** Envoyé par un contrôle rebar lorsque sa hauteur a changé.  
  
-   **RBN\_LAYOUTCHANGED** Envoyé par un contrôle rebar lorsque l'utilisateur modifie la disposition des bandes de contrôle.  
  
 Pour plus d'informations sur ces notifications, consultez la [Référence de contrôle rebar](http://msdn.microsoft.com/library/windows/desktop/bb774375) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)