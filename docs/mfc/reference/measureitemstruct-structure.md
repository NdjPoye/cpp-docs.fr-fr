---
title: "MEASUREITEMSTRUCT, structure | Microsoft Docs"
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
  - "MEASUREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MEASUREITEMSTRUCT (structure)"
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MEASUREITEMSTRUCT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `MEASUREITEMSTRUCT` notifie Windows des dimensions d'un contrôle  owner\-drawn ou d'un élément de menu.  
  
## Syntaxe  
  
```  
  
      typedef struct tagMEASUREITEMSTRUCT {  
   UINT CtlType;  
   UINT CtlID;  
   UINT itemID;  
   UINT itemWidth;  
   UINT itemHeight;  
   DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### Paramètres  
 `CtlType`  
 Contient le type de contrôle.  Les valeurs pour les types de contrôle sont les suivantes :  
  
-   Fenêtre de liste déroulante owner\-draw de **ODT\_COMBOBOX** .  
  
-   Zone de liste owner\-draw d'**ODT\_LISTBOX**  
  
-   **ODT\_MENU** Menu de dessin du possesseur.  
  
 `CtlID`  
 Contient l'ID de contrôle pour une fenêtre de liste déroulante, une zone de liste, ou un bouton.  Ce membre n'est pas utilisé pour le menu.  
  
 `itemID`  
 Contient l'ID de l'élément de menu pour un menu ou ID de la zone de liste pour une zone de liste déroulante ou une zone de liste de variables \(hauteur.  Ce membre n'est pas utilisé pour une zone de liste déroulante ou une zone de liste à altitude fixe, ou pour un bouton.  
  
 *itemWidth*  
 Spécifie la largeur de l'élément de menu.  Le propriétaire de l'élément de menu dessiner doit remplir ce membre avant qu'il retourne du message.  
  
 *itemHeight*  
 Spécifie la hauteur d'un élément contenu dans cette zone de liste ou un menu.  Avant qu'il ne revienne du message, le propriétaire de la zone de liste déroulante owner\-draw, dans la zone de liste, ou de l'élément de menu doit effectuer ce membre.  La hauteur maximale d'un élément de la zone de liste est 255.  
  
 `itemData`  
 Pour une zone de liste déroulante ou une zone de liste, ce membre contient la valeur qui a été transmise à la zone de liste par un des éléments suivants :  
  
-   [CComboBox::AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CListBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CListBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 Pour un projet, ce membre contient la valeur qui a été transmise au menu par un des éléments suivants :  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
 Cela permet à Windows d'utiliser l'interaction avec le contrôle correctement.  L'absence de remplissage des membres appropriés dans la structure de `MEASUREITEMSTRUCT` provoque l'exécution inexact du contrôle.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)