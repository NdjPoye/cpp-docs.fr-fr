---
title: "Fonctions membres couramment substitu&#233;es | Microsoft Docs"
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
  - "CDialog (classe), membres"
  - "classes de boîte de dialogue, fonctions membres couramment substituées"
  - "boîtes de dialogue MFC, substituer des fonctions membres"
  - "OnCancel (fonction)"
  - "OnInitDialog (fonction)"
  - "OnOK (fonction)"
  - "substituer, membres de classe de boîte de dialogue"
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions membres couramment substitu&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant répertorie les fonctions membres les de substituer dans votre classe dérivée de `CDialog`.  
  
### Fonctions membres généralement subtituées de la classe CDialog  
  
|Fonctions membres|Message auquel cela répond|But de la substitution|  
|-----------------------|--------------------------------|----------------------------|  
|`OnInitDialog`|**WM\_INITDIALOG**|Initialisez les contrôles de la boîte de dialogue.|  
|`OnOK`|**BN\_CLICKED** pour le bouton **IDOK**|Répond lorsque l'utilisateur clique sur le bouton OK.|  
|`OnCancel`|**BN\_CLICKED** pour le bouton **IDCANCEL**|Répond lorsque l'utilisateur clique sur le bouton Annuler.|  
  
 `OnInitDialog`, `OnOK`, et `OnCancel` sont des fonctions virtuelles.  Pour les substituer, vous déclarez une fonction substituante dans la classe de la boîte de dialogue dérivée en utilisant [Fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
 `OnInitDialog` est appelée immédiatement avant la boîte de dialogue qui s'affiche.  Vous devez appeler le gestionnaire par défaut `OnInitDialog` de la substitution — généralement comme première action du gestionnaire.  Par défaut, `OnInitDialog` retourne **TRUE** pour indiquer que le focus doit être défini sur le premier contrôle dans la boîte de dialogue.  
  
 `OnOK` est généralement substitué pour des boîtes de dialogue modales et non non\-modales.  Si vous substituez ce handler par une boîte de dialogue modale, appelez la version de la classe de base de la substitution — pour vous assurer que `EndDialog` est appelé — ou appelez `EndDialog` vous\-même.  
  
 `OnCancel` est généralement substitué pour les boîtes de dialogue non modales.  
  
 Pour plus d'informations sur ces fonctions membres, consultez la classe [CDialog](../mfc/reference/cdialog-class.md) dans *le guide de MFC* et la discussion sur le [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md).  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Fonctions membres couramment ajoutées](../mfc/commonly-added-member-functions.md)