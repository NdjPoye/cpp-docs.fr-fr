---
title: "CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IMAGE_EDIT_MODE Enumeration"
  - "CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration"
  - "CMFCImagePaintArea.IMAGE_EDIT_MODE Enumeration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMAGE_EDIT_MODE méthode d'énumération"
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un mode dessin que vous utilisez pour modifier une image dans une boîte de dialogue éditeur d'image.  
  
## Syntaxe  
  
```  
enum IMAGE_EDIT_MODE  
{  
   IMAGE_EDIT_MODE_PEN = 0,  
   IMAGE_EDIT_MODE_FILL,  
   IMAGE_EDIT_MODE_LINE,  
   IMAGE_EDIT_MODE_RECT,  
   IMAGE_EDIT_MODE_ELLIPSE,  
   IMAGE_EDIT_MODE_COLOR  
};  
```  
  
## Membres  
  
|||  
|-|-|  
|Nom|Description|  
|`IMAGE_EDIT_MODE_PEN`|Utilisé pour ajouter des pixels.|  
|`IMAGE_EDIT_MODE_FILL`|Utilisé pour remplir les zones adjacentes qui contiennent la couleur à l'emplacement du curseur actuel.|  
|`IMAGE_EDIT_MODE_LINE`|Pour tracer une ligne|  
|`IMAGE_EDIT_MODE_RECT`|Utilisé pour dessiner un rectangle|  
|`IMAGE_EDIT_MODE_ELLIPSE`|Utilisé pour ajouter une ellipse.|  
|`IMAGE_EDIT_MODE_COLOR`|Utilisé pour définir la couleur actuelle à la couleur à l'emplacement du curseur actuel.|  
  
### Remarques  
 Les classes d'`CMFCImagePaintArea` et d'`CMFCImageEditorDialog` utilisent cette énumération pour définir le mode de dessin actuel.  Mode dessin et la couleur actuelle sont utilisés pour modifier la zone d'image dans une boîte de dialogue éditeur d'image.  Pour plus d’informations sur `CMFCImagePaintArea` et `CMFCImageEditorDialog`, voir [CMFCImagePaintArea Class](../../mfc/reference/cmfcimagepaintarea-class.md) et [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 Lorsque vous sélectionnez une couleur dans une image à l'aide de le mode dessin représentant `IMAGE_EDIT_MODE_COLOR`, l'infrastructure définit le mode de dessin à `IMAGE_EDIT_MODE_PEN`.  
  
## Configuration requise  
 **En\-tête :** afximagepaintarea.h  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea Class](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)