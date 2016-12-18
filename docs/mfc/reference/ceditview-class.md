---
title: "CEditView Class | Microsoft Docs"
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
  - "CEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEditView class"
  - "edit controls, classes"
  - "text editors"
  - "text editors, CEditView class"
  - "vues, classes"
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un type de classe d'affichage qui fournit les fonctionnalités d'un contrôle d'édition windows et peut être utilisée pour implémenter la fonctionnalité simple d'éditeur de texte.  
  
## Syntaxe  
  
```  
class CEditView : public CCtrlView  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CEditView::CEditView](../Topic/CEditView::CEditView.md)|Crée un objet avec du type `CEditView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CEditView::FindText](../Topic/CEditView::FindText.md)|Recherche une chaîne dans le texte.|  
|[CEditView::GetBufferLength](../Topic/CEditView::GetBufferLength.md)|Obtient la longueur de la mémoire tampon de caractères.|  
|[CEditView::GetEditCtrl](../Topic/CEditView::GetEditCtrl.md)|Permet d'accéder à la partie d' `CEdit` d'un objet d' `CEditView` \(le contrôle d'édition windows\).|  
|[CEditView::GetPrinterFont](../Topic/CEditView::GetPrinterFont.md)|Extrait la police d'imprimante actuelle.|  
|[CEditView::GetSelectedText](../Topic/CEditView::GetSelectedText.md)|Extrait la sélection actuelle de texte.|  
|[CEditView::LockBuffer](../Topic/CEditView::LockBuffer.md)|Verrouille la mémoire tampon.|  
|[CEditView::PrintInsideRect](../Topic/CEditView::PrintInsideRect.md)|Affiche le texte à l'intérieur d'un rectangle donné.|  
|[CEditView::SerializeRaw](../Topic/CEditView::SerializeRaw.md)|Sérialise un objet d' `CEditView` sur le disque en tant que texte brut.|  
|[CEditView::SetPrinterFont](../Topic/CEditView::SetPrinterFont.md)|Définit une nouvelle police d'imprimante.|  
|[CEditView::SetTabStops](../Topic/CEditView::SetTabStops.md)|Définit des taquets de tabulation pour l'écran et l'impression.|  
|[CEditView::UnlockBuffer](../Topic/CEditView::UnlockBuffer.md)|Déverrouille la mémoire tampon.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CEditView::OnFindNext](../Topic/CEditView::OnFindNext.md)|L'occurrence de recherche d'une chaîne de texte.|  
|[CEditView::OnReplaceAll](../Topic/CEditView::OnReplaceAll.md)|Remplace toutes les occurrences d'une chaîne fournie par une nouvelle chaîne.|  
|[CEditView::OnReplaceSel](../Topic/CEditView::OnReplaceSel.md)|Remplace la sélection actuelle.|  
|[CEditView::OnTextNotFound](../Topic/CEditView::OnTextNotFound.md)|Appelé lorsqu'une opération de recherche ne correspond pas moins le texte.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CEditView::dwStyleDefault](../Topic/CEditView::dwStyleDefault.md)|Style par défaut pour les objets de type **CEditView.**|  
  
## Notes  
 La classe d' `CEditView` fournit des fonctions supplémentaires suivantes :  
  
-   Copie.  
  
-   Recherchez et remplacez.  
  
 Étant donné que la classe `CEditView` est un dérivé de la classe `CView`, les objets de la classe `CEditView` peuvent être utilisés avec des documents et des modèles de document.  
  
 Le texte de chaque contrôle d' `CEditView` est conservé dans son propre objet stockage global.  Votre application peut avoir plusieurs objets d' `CEditView` .  
  
 Créez les objets de type `CEditView` si vous souhaitez une fenêtre de modification avec la fonctionnalité ajoutée répertoriée ci\-dessus, ou si vous souhaitez que la fonctionnalité simple d'éditeur de texte.  Un objet d' `CEditView` peut occuper la zone cliente entière d'une fenêtre.  Dérivez vos propres classes d' `CEditView` pour ajouter ou modifier les fonctionnalités de base, ou pour déclarer des classes qui peuvent être ajoutées à un modèle de document.  
  
 L'implémentation par défaut de la classe `CEditView` gère les commandes suivantes : **ID\_EDIT\_SELECT\_ALL**, **ID\_EDIT\_FIND**, **ID\_EDIT\_REPLACE**, **ID\_EDIT\_REPEAT**, et **ID\_FILE\_PRINT**.  
  
 La limite par défaut de caractère pour `CEditView` est \(1024 x 1024 à 1 \= 1048575\).  Cela peut être modifié en appelant la fonction d' **EM\_LIMITTEXT** du contrôle d'édition sous\-jacent.  Toutefois, les limites sont différentes selon le système d'exploitation et le type de contrôle edit \(unique ou multiligne\).  Pour plus d'informations sur ces limites, consultez l' [EM\_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 Pour modifier cette limite dans votre contrôle, substituez la fonction d' `OnCreate()` pour votre classe d' `CEditView` et insérez la ligne de code suivante :  
  
 [!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/CPP/ceditview-class_1.cpp)]  
  
 Les objets de type `CEditView` \(ou de types dérivés d' `CEditView`\) ont les limitations suivantes :  
  
-   `CEditView` n'implémente pas vrai quel est vous constatez que vous obtenez la modification de \(WYSIWYG\).  Où il existe un choix entre la lisibilité à l'écran et la sortie imprimée par correspondance, `CEditView` opte pour la lisibilité d'écran.  
  
-   `CEditView` peuvent le texte affiché uniquement dans une police unique.  Aucune mise en forme de caractère spécial n'est pris en charge.  Consultez la classe [CRichEditView](../../mfc/reference/cricheditview-class.md) pour les fonctionnalités supérieures.  
  
-   La quantité de texte que `CEditView` peut contenir est limitée.  Les limites sont les mêmes que pour le contrôle d' `CEdit` .  
  
 Pour plus d'informations sur `CEditView`, consultez [classes d'affichage dérivées disponibles dans MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [exemple MFC SUPERPAD](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)