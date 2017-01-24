---
title: "CMFCColorDialog Class | Microsoft Docs"
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
  - "CMFCColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorDialog class"
  - "CMFCColorDialog::m_bIsMyPalette data member"
  - "CMFCColorDialog::m_bPickerMode data member"
  - "CMFCColorDialog::m_btnColorSelect data member"
  - "CMFCColorDialog::m_CurrentColor data member"
  - "CMFCColorDialog::m_hcurPicker data member"
  - "CMFCColorDialog::m_NewColor data member"
  - "CMFCColorDialog::m_pColourSheetOne data member"
  - "CMFCColorDialog::m_pColourSheetTwo data member"
  - "CMFCColorDialog::m_pPalette data member"
  - "CMFCColorDialog::m_pPropSheet data member"
  - "CMFCColorDialog::m_wndColors data member"
  - "CMFCColorDialog::m_wndStaticPlaceHolder data member"
  - "CMFCColorDialog::PreTranslateMessage method"
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCColorDialog` représente une boîte de dialogue de sélection de couleurs.  
  
## Syntaxe  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](../Topic/CMFCColorDialog::CMFCColorDialog.md)|Construit un objet `CMFCColorDialog`.|  
|`CMFCColorDialog::~CMFCColorDialog`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorDialog::GetColor](../Topic/CMFCColorDialog::GetColor.md)|Retourne la couleur sélectionnée par actuel.|  
|[CMFCColorDialog::GetPalette](../Topic/CMFCColorDialog::GetPalette.md)|Retourne la palette de couleurs.|  
|`CMFCColorDialog::PreTranslateMessage`|Traduit des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  Pour la syntaxe et plus d'informations, consultez [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Substitutions `CDialogEx::PreTranslateMessage`.\)|  
|[CMFCColorDialog::RebuildPalette](../Topic/CMFCColorDialog::RebuildPalette.md)|Dérive une palette de la palette système.|  
|[CMFCColorDialog::SetCurrentColor](../Topic/CMFCColorDialog::SetCurrentColor.md)|Définit la couleur sélectionnée par actuel.|  
|[CMFCColorDialog::SetNewColor](../Topic/CMFCColorDialog::SetNewColor.md)|Définit la couleur la plus équivalente à une valeur RVB spécifiée.|  
|[CMFCColorDialog::SetPageOne](../Topic/CMFCColorDialog::SetPageOne.md)|Sélectionne une valeur RVB pour la première page de propriétés.|  
|[CMFCColorDialog::SetPageTwo](../Topic/CMFCColorDialog::SetPageTwo.md)|Sélectionne une valeur RVB pour la deuxième page de propriétés.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|`m_bIsMyPalette`|`TRUE` si la boîte de dialogue de sélection de couleurs utilise sa propre palette couleurs, ou `FALSE` si la boîte de dialogue utilise une palette qui est spécifiée dans le constructeur d' `CMFCColorDialog` .|  
|`m_bPickerMode`|`TRUE` lorsque l'utilisateur sélectionne une couleur dans la boîte de dialogue de sélection ; sinon, `FALSE`.|  
|`m_btnColorSelect`|Le bouton de couleur que l'utilisateur a sélectionné.|  
|`m_CurrentColor`|La couleur sélectionnée.|  
|`m_hcurPicker`|Le curseur qui permet de choisir une couleur.|  
|`m_NewColor`|La couleur sélectionnée éventuelle, qui peut être définitivement sélectionnée ou rétablie à la couleur d'origine.|  
|`m_pColourSheetOne`|Un pointeur vers la première page de propriétés de la feuille de propriétés de sélection de couleurs.|  
|`m_pColourSheetTwo`|Un pointeur vers la deuxième page de propriétés de la feuille de propriétés de sélection de couleurs.|  
|`m_pPalette`|La palette logique actuelle.|  
|`m_pPropSheet`|Un pointeur à la feuille de propriétés de la boîte de dialogue de sélection de couleurs.|  
|`m_wndColors`|Un objet contrôle de sélecteur de couleurs.|  
|`m_wndStaticPlaceHolder`|Un contrôle statique qui est un espace réservé pour la feuille de propriétés de sélecteur de couleurs.|  
  
## Notes  
 La boîte de dialogue de sélection de couleurs est affichée comme feuille de propriétés avec deux pages.  Sur la première page, vous sélectionnez une couleur standard de la palette système ; dans la deuxième page, vous sélectionnez une couleur personnalisée.  
  
 Vous pouvez construire un objet d' `CMFCColorDialog` sur la pile puis appeler `DoModal`, en passant la couleur initiale comme paramètre au constructeur d' `CMFCColorDialog` .  La boîte de dialogue de sélection de couleurs crée ensuite plusieurs objets de [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md) pour gérer chaque palette de couleurs.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## Exemple  
 L'exemple suivant montre comment configurer une boîte de dialogue couleur en utilisant différentes méthodes dans la classe d' `CMFCColorDialog` .  L'exemple illustre comment définir le actuel et les nouvelles couleurs de dialogue, et comment définir les composantes rouge, vert et bleu, d'une couleur sélectionnée sur les deux pages de propriétés de la boîte de dialogue couleur.  Cet exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/CPP/cmfccolordialog-class_1.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxcolordialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md)