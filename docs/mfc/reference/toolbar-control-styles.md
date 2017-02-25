---
title: "Styles de contr&#244;le ToolBar | Microsoft Docs"
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
  - "ToolBar (styles de contrôle)"
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Styles de contr&#244;le ToolBar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md) possède un ensemble d'indicateurs de style qui déterminent l'apparence et le comportement du bouton.  Définissez une combinaison de ces indicateurs en appelant [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md).  Cette rubrique répertorie les valeurs d'indicateur de style et leurs significations.  
  
## Valeurs de la propriété  
 Les valeurs suivantes déterminent le type de bouton que le contrôle représente :  
  
 TBBS\_BUTTON  
 Bouton poussoir standard \(valeur par défaut\).  
  
 TBBS\_CHECKBOX  
 Case à cocher.  
  
 TBBS\_CHECKGROUP  
 Le début d'un groupe de cases à cocher.  
  
 TBBS\_GROUP  
 Le début d'un groupe de boutons.  
  
 TBBS\_SEPARATOR  
 Separateur.  
  
 Les valeurs suivantes représentent l'état actuel du contrôle :  
  
 TBBS\_CHECKED  
 La case à cocher est cochée.  
  
 TBBS\_DISABLED  
 Le contrôle est désactivé.  
  
 TBBS\_INDETERMINATE  
 La case à cocher est dans un état indéterminé.  
  
 TBBS\_PRESSED  
 Le bouton est appuyé.  
  
 La valeur suivante modifie la disposition du bouton dans la barre d'outils :  
  
 TBBS\_BREAK  
 Place l'élément sur une nouvelle ligne ou dans une nouvelle colonne sans séparer les colonnes.  
  
## Notes  
 Le style actuel est stocké dans [CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md).  Ne définissez pas la valeur dans `m_nStyle` directement, car certaines classes dérivées effectuent le traitement supplémentaire requis lorsque vous appelez `SetStyles`.  
  
 Le gestionnaire visuel détermine l'apparence des boutons dans chaque état.  Pour plus d'informations, consultez [Gestionnaire de visualisation](../../mfc/visualization-manager.md).  
  
## Conditions requises  
 **En\-tête :** afxtoolbarbutton.h  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Gestionnaire de visualisation](../../mfc/visualization-manager.md)