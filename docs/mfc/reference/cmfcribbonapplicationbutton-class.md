---
title: "CMFCRibbonApplicationButton Class | Microsoft Docs"
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
  - "CMFCRibbonApplicationButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonApplicationButton class"
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonApplicationButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un bouton spécial située dans l'angle supérieur gauche de la fenêtre d'application.  Lorsque vous cliquez sur le bouton, ouvre un menu qui contient généralement des commandes courantes **Fichier** comme **Ouvrir**, **Enregistrer**, et **Quitter**.  
  
## Syntaxe  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](../Topic/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton.md)|Les éléments et initialise un objet d' `CMFCRibbonApplicationButton` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCRibbonApplicationButton::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCRibbonApplicationButton::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCRibbonApplicationButton::SetImage](../Topic/CMFCRibbonApplicationButton::SetImage.md)|Affecte une image à la touche application de ruban.|  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCRibbonApplicationButton` .  L'exemple indique comment assigner une image à la touche application, et comment définir son info\-bulle.  Cet extrait de code fait partie d' [Exemple de client de dessin](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/CPP/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/CPP/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxRibbonBar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)