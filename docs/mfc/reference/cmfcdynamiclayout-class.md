---
title: "CMFCDynamicLayout Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: 16
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDynamicLayout Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie comment les contrôles dans une fenêtre sont déplacés et redimensionnés à mesure que l'utilisateur redimensionne la fenêtre.  
  
## Syntaxe  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|Construit un objet `CMFCDynamicLayout`.|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md)|Ajoute une fenêtre enfant, généralement un contrôle, à la liste des fenêtres contrôlées par le gestionnaire de disposition dynamique.|  
|[CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md)|Ajoute une fenêtre enfant, généralement un contrôle, à la liste des fenêtres contrôlées par le gestionnaire de disposition dynamique.|  
|[CMFCDynamicLayout::Create](../Topic/CMFCDynamicLayout::Create.md)|Stocke et valide la fenêtre hôte.|  
|[CMFCDynamicLayout::GetHostWnd](../Topic/CMFCDynamicLayout::GetHostWnd.md)|Retourne un pointeur vers une fenêtre hôte.|  
|[CMFCDynamicLayout::GetMinSize](../Topic/CMFCDynamicLayout::GetMinSize.md)|Retourne la taille de fenêtre en dessous de laquelle la disposition n'est pas ajustée.|  
|[CMFCDynamicLayout::GetWindowRect](../Topic/CMFCDynamicLayout::GetWindowRect.md)|Récupère le rectangle pour la zone cliente active de la fenêtre.|  
|[CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md)|Vérifie si un contrôle enfant a été ajouté à la disposition dynamique.|  
|[CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md)|Vérifie qu'aucune fenêtre enfant n'a été ajoutée à une disposition dynamique.|  
|[CMFCDynamicLayout::LoadResource](../Topic/CMFCDynamicLayout::LoadResource.md)|Lit la disposition dynamique de la ressource AFX\_DIALOG\_LAYOUT, puis applique la disposition à la fenêtre hôte.|  
|static [CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md)|Obtient une valeur [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) qui définit l'amplitude du déplacement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne sa fenêtre hôte.|  
|static [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md)|Obtient une valeur [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) qui définit l'amplitude du déplacement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne sa fenêtre hôte.|  
|static [CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md)|Obtient une valeur [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) qui représente une absence d'animation, verticale ou horizontale, pour un contrôle enfant.|  
|static [CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md)|Obtient une valeur [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) qui définit l'amplitude du déplacement d'un contrôle enfant sur le plan vertical quand l'utilisateur redimensionne sa fenêtre hôte.|  
|[CMFCDynamicLayout::SetMinSize](../Topic/CMFCDynamicLayout::SetMinSize.md)|Définit la taille de fenêtre en dessous de laquelle la disposition n'est pas ajustée.|  
|static [CMFCDynamicLayout::SizeHorizontal](../Topic/CMFCDynamicLayout::SizeHorizontal.md)|Obtient une valeur [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) qui définit l'amplitude du redimensionnement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne sa fenêtre hôte.|  
|static [CMFCDynamicLayout::SizeHorizontalAndVertical](../Topic/CMFCDynamicLayout::SizeHorizontalAndVertical.md)|Obtient une valeur [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) qui définit l'amplitude du redimensionnement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne sa fenêtre hôte.|  
|static [CMFCDynamicLayout::SizeNone](../Topic/CMFCDynamicLayout::SizeNone.md)|Obtient une valeur [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) qui représente une absence de changement de taille pour un contrôle enfant.|  
|static [CMFCDynamicLayout::SizeVertical](../Topic/CMFCDynamicLayout::SizeVertical.md)|Obtient une valeur [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) qui définit l'amplitude du redimensionnement d'un contrôle enfant sur le plan vertical quand l'utilisateur redimensionne sa fenêtre hôte.|  
  
## Types imbriqués  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDynamicLayout::MoveSettings, structure](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)|Encapsule les données de déplacement des contrôles dans une disposition dynamique.|  
|[CMFCDynamicLayout::SizeSettings, structure](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)|Encapsule les données de changement de taille des contrôles dans une disposition dynamique.|  
  
## Notes  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## Configuration requise  
 **En\-tête :** afxlayout.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)