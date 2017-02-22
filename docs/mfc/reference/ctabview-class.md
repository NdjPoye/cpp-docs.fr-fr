---
title: "CTabView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTabView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabView class"
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CTabView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CTabView` simplifie l'utilisation de la classe de contrôle onglet \([CMFCTabCtrl](../../mfc/reference/ctabview-class.md)\) dans les applications qui utilisent l'architecture Document\/Vue MFC.  
  
## Syntaxe  
  
```  
class CTabbedView : public CView  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTabView::AddView](../Topic/CTabView::AddView.md)|Ajoute une nouvelle vue au contrôle onglet.|  
|[CTabView::FindTab](../Topic/CTabView::FindTab.md)|Retourne l'index de la vue spécifiée dans le contrôle onglet.|  
|[CTabView::GetActiveView](../Topic/CTabView::GetActiveView.md)|Retourne un pointeur actuel \- à la vue active|  
|[CTabView::GetTabControl](../Topic/CTabView::GetTabControl.md)|Retourne une référence au contrôle onglet associé à la vue.|  
|[CTabView::RemoveView](../Topic/CTabView::RemoveView.md)|Supprime l'affichage de contrôle tab.|  
|[CTabView::SetActiveView](../Topic/CTabView::SetActiveView.md)|Rend une vue active.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CTabView::IsScrollBar](../Topic/CTabView::IsScrollBar.md)|Appelé par l'infrastructure en créant une vue d'onglet pour déterminer si l'affichage d'onglet contient une barre de défilement horizontale partagée.|  
|[CTabView::OnActivateView](../Topic/CTabView::OnActivateView.md)|Appelé par l'infrastructure lorsque la vue d'onglet est rendue active ou inactive.|  
  
## Notes  
 Cette classe facilite de mettre une vue à onglets dans une application de document\/vue.  `CTabView` est `CView`\- la classe dérivée qui contient un objet incorporé d' `CMFCTabCtrl` .  `CTabView` gère tous les messages requis pour prendre en charge l'objet d' `CMFCTabCtrl` .  Dérivez simplement une classe d' `CTabView` et branchez\- à votre application, puis ajoutez `CView`\- classes dérivées à l'aide de la méthode d' `AddView` .  Le contrôle onglet affiche ces vues comme onglets.  
  
 Par exemple, vous pouvez avoir un document qui peut être représenté de différentes façons : comme une feuille de calcul, un graphique, un formulaire modifiable, et ainsi de suite.  Vous pouvez créer différentes vues dessinant les données si nécessaire, les insérer dans votre `CTabView`objet dérivé et les faire tabulation sans codage supplémentaire.  
  
 [Exemple TabbedView : MFC est tabulé l'application de vue](../../top/visual-cpp-samples.md) illustre l'utilisation d' `CTabView`.  
  
## Exemple  
 L'exemple suivant montre comment `CTabView` est utilisé dans l'exemple TabbedView.  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/CPP/ctabview-class_1.h)]  
  
## Configuration requise  
 **en\-tête :** afxTabView.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CTabView Class](../../mfc/reference/ctabview-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)