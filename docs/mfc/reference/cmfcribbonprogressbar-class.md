---
title: "CMFCRibbonProgressBar Class | Microsoft Docs"
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
  - "CMFCRibbonProgressBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonProgressBar class"
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonProgressBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un contrôle qui indique visuellement la progression d'une longue opération.  
  
## Syntaxe  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](../Topic/CMFCRibbonProgressBar::CMFCRibbonProgressBar.md)|Les éléments et initialise un objet d' `CMFCRibbonProgressBar` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](../Topic/CMFCRibbonProgressBar::GetPos.md)|Retourne la progression actuelle.|  
|[CMFCRibbonProgressBar::GetRangeMax](../Topic/CMFCRibbonProgressBar::GetRangeMax.md)|Retourne la valeur maximale de la plage actuel.|  
|[CMFCRibbonProgressBar::GetRangeMin](../Topic/CMFCRibbonProgressBar::GetRangeMin.md)|Retourne la valeur minimale de la plage actuel.|  
|[CMFCRibbonProgressBar::GetRegularSize](../Topic/CMFCRibbonProgressBar::GetRegularSize.md)|Retourne la taille normale de l'élément ruban.  \(Substitutions [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](../Topic/CMFCRibbonProgressBar::IsInfiniteMode.md)|Spécifie si la barre de progression s'exécute en mode infini.|  
|[CMFCRibbonProgressBar::OnDraw](../Topic/CMFCRibbonProgressBar::OnDraw.md)|Appelé par l'infrastructure pour dessiner l'élément ruban.  \(Substitutions [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md).\)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](../Topic/CMFCRibbonProgressBar::SetInfiniteMode.md)|Définit la barre de progression pour fonctionner en mode infini.|  
|[CMFCRibbonProgressBar::SetPos](../Topic/CMFCRibbonProgressBar::SetPos.md)|Définit la progression actuelle.|  
|[CMFCRibbonProgressBar::SetRange](../Topic/CMFCRibbonProgressBar::SetRange.md)|Définit les valeurs minimales et maximales.|  
  
## Notes  
 `CMFCRibbonProgressBar` peut s'exécuter dans deux modes : normal et l'infini.  En mode normal, la barre de progression est remplie de gauche à droite et s'arrête lorsqu'elle atteint la valeur maximale.  En mode infini, la barre de progression est répétée remplie de la valeur minimale à la valeur maximale.  Vous pouvez utiliser le mode infinity pour indiquer qu'une opération est en cours, mais que le temps d'achèvement est inconnu.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCRibbonProgressBar` .  L'exemple montre comment définir la barre de progression pour fonctionner en mode infini \(où la période d'achèvement d'une opération est inconnu\), pour définir les valeurs minimales et maximales la barre de progression, et pour définir la position actuelle de la barre de progression.  Cet extrait de code fait partie d' [Exemple 2007 de démonstration de MS Office](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/CPP/cmfcribbonprogressbar-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxRibbonProgressBar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)