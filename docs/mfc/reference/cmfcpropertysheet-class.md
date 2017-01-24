---
title: "CMFCPropertySheet Class | Microsoft Docs"
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
  - "CMFCPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertySheet class"
  - "CMFCPropertySheet::OnInitDialog method"
  - "CMFCPropertySheet::PreTranslateMessage method"
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe `CMFCPropertySheet` prend en charge une feuille de propriétés où chaque page de propriétés est représentée par un onglet de page, un bouton de barre d'outils, un nœud de contrôle d'arborescence ou un élément de liste.  
  
## Syntaxe  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](../Topic/CMFCPropertySheet::CMFCPropertySheet.md)|Construit un objet `CMFCPropertySheet`.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|Destructeur.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md)|Ajoute une page à la feuille de propriétés.|  
|[CMFCPropertySheet::AddPageToTree](../Topic/CMFCPropertySheet::AddPageToTree.md)|Ajoute une nouvelle page de propriétés au contrôle d'arborescence.|  
|[CMFCPropertySheet::AddTreeCategory](../Topic/CMFCPropertySheet::AddTreeCategory.md)|Ajoute un nouveau nœud au contrôle d'arborescence.|  
|[CMFCPropertySheet::EnablePageHeader](../Topic/CMFCPropertySheet::EnablePageHeader.md)|Réserve de l'espace en haut de chaque page pour dessiner un en\-tête personnalisé.|  
|[CMFCPropertySheet::GetHeaderHeight](../Topic/CMFCPropertySheet::GetHeaderHeight.md)|Récupère la hauteur de l'en\-tête actuel.|  
|[CMFCPropertySheet::GetLook](../Topic/CMFCPropertySheet::GetLook.md)|Récupère une valeur d'énumération qui spécifie l'apparence de la feuille de propriétés actuelle.|  
|[CMFCPropertySheet::GetNavBarWidth](../Topic/CMFCPropertySheet::GetNavBarWidth.md)|Réessaie la largeur de la barre de navigation en pixels.|  
|[CMFCPropertySheet::GetTab](../Topic/CMFCPropertySheet::GetTab.md)|Récupère l'objet de contrôle d'onglet interne qui prend en charge le contrôle de feuille de propriétés actuel.|  
|`CMFCPropertySheet::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCPropertySheet::InitNavigationControl](../Topic/CMFCPropertySheet::InitNavigationControl.md)|Initialise l'apparence du contrôle de feuille de propriétés actuel.|  
|[CMFCPropertySheet::OnActivatePage](../Topic/CMFCPropertySheet::OnActivatePage.md)|Appelé par l'infrastructure quand une page de propriétés est activée.|  
|[CMFCPropertySheet::OnDrawPageHeader](../Topic/CMFCPropertySheet::OnDrawPageHeader.md)|Appelé par l'infrastructure pour dessiner un en\-tête de page de propriétés personnalisé.|  
|`CMFCPropertySheet::OnInitDialog`|Gère le message [WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428).  \(Substitue [CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md).\)|  
|[CMFCPropertySheet::OnRemoveTreePage](../Topic/CMFCPropertySheet::OnRemoveTreePage.md)|Appelé par l'infrastructure pour supprimer une page de propriétés d'un contrôle d'arborescence.|  
|`CMFCPropertySheet::PreTranslateMessage`|Traduit les messages de fenêtre avant d'être distribués aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  \(Substitue `CPropertySheet::PreTranslateMessage`.\)|  
|[CMFCPropertySheet::RemoveCategory](../Topic/CMFCPropertySheet::RemoveCategory.md)|Supprime un nœud du contrôle d'arborescence.|  
|[CMFCPropertySheet::RemovePage](../Topic/CMFCPropertySheet::RemovePage.md)|Supprime une page de propriétés de la feuille de propriétés.|  
|[CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md)|Spécifie la liste des images utilisées dans le contrôle de navigation du volet Outlook.|  
|[CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md)|Spécifie l'apparence de la feuille de propriétés.|  
  
## Notes  
 La classe `CMFCPropertySheet` représente les feuilles de propriétés, aussi appelées boîtes de dialogue à onglets.  La classe `CMFCPropertySheet` peut afficher une page de propriétés de diverses manières.  
  
 Pour utiliser la classe `CMFCPropertySheet` dans votre application, procédez comme suit :  
  
1.  Faites dériver une classe de la classe `CMFCPropertySheet` et nommez\-la, par exemple, CMyPropertySheet.  
  
2.  Construisez un objet [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) pour chaque page de propriétés.  
  
3.  Appelez la méthode [CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md) dans le constructeur CMyPropertySheet.  Un paramètre de cette méthode permet de spécifier sous quelle forme les pages de propriétés seront affichées : onglets le long de la bordure supérieure ou gauche de la feuille de propriétés ; onglets dans le style d'une feuille de propriétés Microsoft OneNote ; boutons sur un contrôle de barre d'outils Microsoft Outlook ; nœuds sur un contrôle d'arborescence ; ou liste d'éléments sur le côté gauche de la feuille de propriétés.  
  
4.  Si vous créez une feuille de propriétés dans le style d'une barre d'outils Microsoft Outlook, appelez la méthode [CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md) pour associer une liste d'images aux pages de propriétés.  
  
5.  Appelez la méthode [CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md) pour chaque page de propriétés.  
  
6.  Créez un contrôle `CMFCPropertySheet` et appelez sa méthode `DoModal`.  
  
## Illustrations  
 L'illustration suivante représente une feuille de propriétés dont le style est celui d'une barre d'outils Microsoft Outlook incorporée.  La barre d'outils Outlook s'affiche sur le côté gauche de la feuille de propriétés.  
  
 ![Contrôles des couleurs CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet\_color")  
  
 L'illustration suivante représente une feuille de propriétés qui contient un objet de la [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  Cet objet est une feuille de propriétés dont le style est celui d'une feuille de propriétés de contrôles communs standard.  
  
 ![Contrôles de liste et de propriété CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet\_list")  
  
 L'illustration suivante représente une feuille de propriétés dont le style est celui d'un contrôle d'arborescence.  
  
 ![Arborescence de propriétés](../../mfc/reference/media/proptree.png "PropTree")  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## Configuration requise  
 **En\-tête :** afxpropertysheet.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage Class](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)