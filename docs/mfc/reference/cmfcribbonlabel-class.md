---
title: "CMFCRibbonLabel Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonLabel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonLabel class"
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonLabel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une étiquette de texte non interactive pour un ruban.  
  
## Syntaxe  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](../Topic/CMFCRibbonLabel::CMFCRibbonLabel.md)|Les éléments et initialise un objet d' `CMFCRibbonLabel` avec la chaîne de texte spécifiée.|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCRibbonLabel::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCRibbonLabel::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCRibbonLabel::SetACCData](../Topic/CMFCRibbonLabel::SetACCData.md)|Détermine les données d'accessibilité pour l'élément actuel d'étiquette de ruban.  \(Substitutions [CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md).\)|  
  
### Remarques  
 Après avoir créé une étiquette de ruban, ajoutez \-la dans un panneau en appelant [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).  
  
 Vous ne pouvez pas ajouter une étiquette de ruban à la Barre d'outils Accès rapide.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## Configuration requise  
 **en\-tête :** afxRibbonLabel.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)