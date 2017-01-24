---
title: "CMFCRibbonStatusBar Class | Microsoft Docs"
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
  - "CMFCRibbonStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonStatusBar class"
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCRibbonStatusBar` implémente un contrôle de barre d'état qui peut afficher des éléments du ruban.  
  
## Syntaxe  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](../Topic/CMFCRibbonStatusBar::AddDynamicElement.md)|Ajoute un élément dynamique à la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::AddElement](../Topic/CMFCRibbonStatusBar::AddElement.md)|Ajoute un nouvel élément ruban à la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::AddExtendedElement](../Topic/CMFCRibbonStatusBar::AddExtendedElement.md)|Ajoute un élément ruban à l'aire étendue de la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::AddSeparator](../Topic/CMFCRibbonStatusBar::AddSeparator.md)|Ajoute un séparateur à la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::Create](../Topic/CMFCRibbonStatusBar::Create.md)|Crée une barre d'état du ruban.|  
|[CMFCRibbonStatusBar::CreateEx](../Topic/CMFCRibbonStatusBar::CreateEx.md)|Crée une barre d'état du ruban avec un style étendu.|  
|[CMFCRibbonStatusBar::FindByID](../Topic/CMFCRibbonStatusBar::FindByID.md)||  
|[CMFCRibbonStatusBar::FindElement](../Topic/CMFCRibbonStatusBar::FindElement.md)|Retourne un pointeur vers l'élément dont l'ID de commande spécifiée|  
|[CMFCRibbonStatusBar::GetCount](../Topic/CMFCRibbonStatusBar::GetCount.md)|Retourne le nombre d'éléments définis de développement ordre la zone principale de la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::GetElement](../Topic/CMFCRibbonStatusBar::GetElement.md)|Retourne un pointeur vers l'élément situé à un index spécifié.|  
|[CMFCRibbonStatusBar::GetExCount](../Topic/CMFCRibbonStatusBar::GetExCount.md)|Retourne le nombre d'éléments définis dans l'aire étendue de la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::GetExElement](../Topic/CMFCRibbonStatusBar::GetExElement.md)|Retourne un pointeur vers l'élément situé à un index spécifié dans l'aire étendue de la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::GetExtendedArea](../Topic/CMFCRibbonStatusBar::GetExtendedArea.md)||  
|[CMFCRibbonStatusBar::GetSpace](../Topic/CMFCRibbonStatusBar::GetSpace.md)||  
|[CMFCRibbonStatusBar::IsBottomFrame](../Topic/CMFCRibbonStatusBar::IsBottomFrame.md)||  
|[CMFCRibbonStatusBar::IsExtendedElement](../Topic/CMFCRibbonStatusBar::IsExtendedElement.md)||  
|[CMFCRibbonStatusBar::IsInformationMode](../Topic/CMFCRibbonStatusBar::IsInformationMode.md)|Détermine si le mode d'informations est activé pour la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::RecalcLayout](../Topic/CMFCRibbonStatusBar::RecalcLayout.md)|\(Substitutions [CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md).\)|  
|[CMFCRibbonStatusBar::RemoveAll](../Topic/CMFCRibbonStatusBar::RemoveAll.md)|Supprime tous les éléments de la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::RemoveElement](../Topic/CMFCRibbonStatusBar::RemoveElement.md)|Supprime l'élément qui a un ID de commande spécifié de la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::SetInformation](../Topic/CMFCRibbonStatusBar::SetInformation.md)|Active ou désactive le mode d'informations pour la barre d'état du ruban.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](../Topic/CMFCRibbonStatusBar::OnDrawInformation.md)|Affiche la chaîne d'information qui apparaît sur la barre d'état du ruban lorsque le mode d'informations est activé.|  
  
## Notes  
 Les utilisateurs peuvent modifier la visibilité des éléments du ruban d'une barre d'état du ruban à l'aide de le menu contextuel prédéfini pour la barre d'état du ruban.  Vous pouvez ajouter ou supprimer des éléments dynamiquement.  
  
 Une barre d'état du ruban a deux zones : un domaine principal et une zone étendue.  La zone étendue s'affiche à droite de la barre d'état de ruban et apparaît dans une couleur différente de la zone principale est.  
  
 En général, la zone principale de la barre d'état affiche des notifications d'état, et la zone étendue affiche des contrôles view.  La zone étendue reste visible aussi longtemps que possible lorsque l'utilisateur redimensionne la barre d'état du ruban.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCRibbonStatusBar` .  L'exemple montre comment ajouter un nouvel élément ruban à la barre d'état du ruban, ajouter un élément ruban à l'aire étendue de la barre d'état du ruban, ajouter un séparateur, et activer le mode normal pour la barre d'état du ruban.  
  
 [!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbar-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxribbonstatusbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)