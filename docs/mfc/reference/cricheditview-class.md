---
title: "CRichEditView Class | Microsoft Docs"
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
  - "CRichEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditView class"
  - "document/view architecture, contrôles RichEdit"
  - "OLE containers, rich edit"
  - "contrôles RichEdit, OLE container"
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avec [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) et [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), fournit les fonctionnalités du contrôle RichEdit dans le contexte de l'architecture de vue du document MFC.  
  
## Syntaxe  
  
```  
  
class CRichEditView : public CCtrlView  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditView::CRichEditView](../Topic/CRichEditView::CRichEditView.md)|Construit un objet `CRichEditView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditView::AdjustDialogPosition](../Topic/CRichEditView::AdjustDialogPosition.md)|Déplace une boîte de dialogue afin qu'elle ne masque pas la sélection actuelle.|  
|[CRichEditView::CanPaste](../Topic/CRichEditView::CanPaste.md)|Indique si le presse\-papiers contient des données qui peuvent être collées dans la vue RichEdit.|  
|[CRichEditView::DoPaste](../Topic/CRichEditView::DoPaste.md)|Colle un élément OLE dans cette vue RichEdit.|  
|[CRichEditView::FindText](../Topic/CRichEditView::FindText.md)|Recherche le texte spécifié, en appelant le curseur d'attente.|  
|[CRichEditView::FindTextSimple](../Topic/CRichEditView::FindTextSimple.md)|Recherche le texte spécifié.|  
|[CRichEditView::GetCharFormatSelection](../Topic/CRichEditView::GetCharFormatSelection.md)|Récupère les attributs de mise en forme de caractères pour la sélection actuelle.|  
|[CRichEditView::GetDocument](../Topic/CRichEditView::GetDocument.md)|Extrait un pointeur vers [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)relatif.|  
|[CRichEditView::GetInPlaceActiveItem](../Topic/CRichEditView::GetInPlaceActiveItem.md)|Extrait l'élément OLE actuellement actif sur place dans la vue RichEdit.|  
|[CRichEditView::GetMargins](../Topic/CRichEditView::GetMargins.md)|Récupère les marges de cette vue RichEdit.|  
|[CRichEditView::GetPageRect](../Topic/CRichEditView::GetPageRect.md)|Récupère le rectangle de page pour cette vue RichEdit.|  
|[CRichEditView::GetPaperSize](../Topic/CRichEditView::GetPaperSize.md)|Récupère le format du papier pour cette vue RichEdit.|  
|[CRichEditView::GetParaFormatSelection](../Topic/CRichEditView::GetParaFormatSelection.md)|Récupère les attributs de mise en forme de paragraphe pour la sélection actuelle.|  
|[CRichEditView::GetPrintRect](../Topic/CRichEditView::GetPrintRect.md)|Récupère le rectangle d'impression pour cette vue RichEdit.|  
|[CRichEditView::GetPrintWidth](../Topic/CRichEditView::GetPrintWidth.md)|Extrait la largeur d'impression pour cette vue RichEdit.|  
|[CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md)|Récupère le contrôle RichEdit.|  
|[CRichEditView::GetSelectedItem](../Topic/CRichEditView::GetSelectedItem.md)|Récupère l'élément sélectionné de la vue RichEdit.|  
|[CRichEditView::GetTextLength](../Topic/CRichEditView::GetTextLength.md)|Extrait la longueur du texte dans la vue RichEdit.|  
|[CRichEditView::GetTextLengthEx](../Topic/CRichEditView::GetTextLengthEx.md)|Récupère le nombre de caractères ou d'octets dans la vue RichEdit.  Liste de balise développée pour la méthode pour déterminer la longueur.|  
|[CRichEditView::InsertFileAsObject](../Topic/CRichEditView::InsertFileAsObject.md)|Insère un fichier comme élément OLE.|  
|[CRichEditView::InsertItem](../Topic/CRichEditView::InsertItem.md)|Insère un nouvel élément en tant qu'élément OLE.|  
|[CRichEditView::IsRichEditFormat](../Topic/CRichEditView::IsRichEditFormat.md)|Indique si le presse\-papiers contient des données dans une modification ou un format texte riche.|  
|[CRichEditView::OnCharEffect](../Topic/CRichEditView::OnCharEffect.md)|Bascule la mise en forme de caractères pour la sélection actuelle.|  
|[CRichEditView::OnParaAlign](../Topic/CRichEditView::OnParaAlign.md)|Modifie l'alignement des paragraphes.|  
|[CRichEditView::OnUpdateCharEffect](../Topic/CRichEditView::OnUpdateCharEffect.md)|Met à jour la commande interface utilisateur pour les fonctions membres publics de caractère.|  
|[CRichEditView::OnUpdateParaAlign](../Topic/CRichEditView::OnUpdateParaAlign.md)|Met à jour la commande interface utilisateur pour les fonctions membres publics de paragraphe.|  
|[CRichEditView::PrintInsideRect](../Topic/CRichEditView::PrintInsideRect.md)|Met en forme le texte spécifié dans le rectangle donné.|  
|[CRichEditView::PrintPage](../Topic/CRichEditView::PrintPage.md)|Met en forme le texte spécifié dans la page donnée.|  
|[CRichEditView::SetCharFormat](../Topic/CRichEditView::SetCharFormat.md)|Définit les attributs de mise en forme de caractères pour la sélection actuelle.|  
|[CRichEditView::SetMargins](../Topic/CRichEditView::SetMargins.md)|Définit les marges de cette vue RichEdit.|  
|[CRichEditView::SetPaperSize](../Topic/CRichEditView::SetPaperSize.md)|Définit le format du papier pour cette vue RichEdit.|  
|[CRichEditView::SetParaFormat](../Topic/CRichEditView::SetParaFormat.md)|Définit les attributs de mise en forme de paragraphe pour la sélection actuelle.|  
|[CRichEditView::TextNotFound](../Topic/CRichEditView::TextNotFound.md)|Réinitialise l'état interne de recherche du contrôle.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditView::GetClipboardData](../Topic/CRichEditView::GetClipboardData.md)|Récupère un objet de presse\-papiers pour une plage dans cette vue RichEdit.|  
|[CRichEditView::GetContextMenu](../Topic/CRichEditView::GetContextMenu.md)|Récupère un menu contextuel à utiliser sur un bouton droit de la souris vers le bas.|  
|[CRichEditView::IsSelected](../Topic/CRichEditView::IsSelected.md)|Indique si le élément OLE donné est sélectionné ou non.|  
|[CRichEditView::OnFindNext](../Topic/CRichEditView::OnFindNext.md)|Recherche l'occurrence d'une sous\-chaîne.|  
|[CRichEditView::OnInitialUpdate](../Topic/CRichEditView::OnInitialUpdate.md)|Actualise une vue lorsqu'elle est d'abord liée à un document.|  
|[CRichEditView::OnPasteNativeObject](../Topic/CRichEditView::OnPasteNativeObject.md)|Récupère les données natives d'un élément OLE.|  
|[CRichEditView::OnPrinterChanged](../Topic/CRichEditView::OnPrinterChanged.md)|Définit les fonctionnalités d'impression à l'appareil donné.|  
|[CRichEditView::OnReplaceAll](../Topic/CRichEditView::OnReplaceAll.md)|Remplace toutes les occurrences d'une chaîne fournie par une nouvelle chaîne.|  
|[CRichEditView::OnReplaceSel](../Topic/CRichEditView::OnReplaceSel.md)|Remplace la sélection actuelle.|  
|[CRichEditView::OnTextNotFound](../Topic/CRichEditView::OnTextNotFound.md)|Traite la notification d'utilisateur qui le texte demandée est introuvable.|  
|[CRichEditView::QueryAcceptData](../Topic/CRichEditView::QueryAcceptData.md)|Requêtes à afficher sur les données sur `IDataObject`.|  
|[CRichEditView::WrapChanged](../Topic/CRichEditView::WrapChanged.md)|Règle le périphérique de sortie cible pour cette vue RichEdit, selon la valeur d' `m_nWordWrap`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRichEditView::m\_nBulletIndent](../Topic/CRichEditView::m_nBulletIndent.md)|Indique la quantité de retrait pour les listes à puces.|  
|[CRichEditView::m\_nWordWrap](../Topic/CRichEditView::m_nWordWrap.md)|Indique les contraintes de retour automatique à la ligne.|  
  
## Notes  
 Un « contrôle RichEdit » est une fenêtre dans laquelle l'utilisateur peut entrer et modifier le texte.  Le texte peut être assigné le caractère et la mise en forme de paragraphe, et peut inclure des objets OLE incorporé.  Les contrôles richedit fournissent une interface de programmation pour le texte de mise en forme.  Toutefois, une application doit implémenter tous les composants d'interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l'utilisateur.  
  
 `CRichEditView` met à jour le texte et la mise en forme caractéristiques du texte.  `CRichEditDoc` met à jour la liste des éléments OLE client qui sont dans la vue.  `CRichEditCntrItem` permet d'accéder au complément aux conteneurs élément OLE client.  
  
 Les contrôles communs Windows \(et par conséquent [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) et les classes connexes\) est disponible uniquement aux programmes s'exécutant sous les versions de Windows 3,51 95\/98 et Windows NT et versions ultérieures.  
  
 Pour obtenir un exemple d'utiliser une vue RichEdit dans une application MFC, consultez l'exemple d'application de [WORDPAD](../../top/visual-cpp-samples.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## Configuration requise  
 **Header:** afxrich.h  
  
## Voir aussi  
 [exemple MFC WORDPAD](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)