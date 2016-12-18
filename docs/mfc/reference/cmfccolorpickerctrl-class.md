---
title: "CMFCColorPickerCtrl Class | Microsoft Docs"
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
  - "CMFCColorPickerCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPickerCtrl class"
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorPickerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCColorPickerCtrl` fournit les fonctionnalités pour un contrôle qui est utilisé pour sélectionner des couleurs.  
  
## Syntaxe  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](../Topic/CMFCColorPickerCtrl::CMFCColorPickerCtrl.md)|Construit un objet `CMFCColorPickerCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](../Topic/CMFCColorPickerCtrl::GetColor.md)|Extrait la couleur que l'utilisateur active.|  
|[CMFCColorPickerCtrl::GetHLS](../Topic/CMFCColorPickerCtrl::GetHLS.md)|Récupère les valeurs de tonalité, de luminosité et de saturation de la couleur que l'utilisateur active.|  
|[CMFCColorPickerCtrl::GetHue](../Topic/CMFCColorPickerCtrl::GetHue.md)|Récupère le composant de tonalité de la couleur que l'utilisateur active.|  
|[CMFCColorPickerCtrl::GetLuminance](../Topic/CMFCColorPickerCtrl::GetLuminance.md)|Récupère le composant de luminosité de la couleur que l'utilisateur active.|  
|[CMFCColorPickerCtrl::GetSaturation](../Topic/CMFCColorPickerCtrl::GetSaturation.md)|Récupère le composant de saturation de la couleur que l'utilisateur active.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](../Topic/CMFCColorPickerCtrl::SelectCellHexagon.md)|Définit la couleur actuelle à la couleur définie par les composants de couleur spécifiés RVB ou l'hexagone de cellule spécifié.|  
|[CMFCColorPickerCtrl::SetColor](../Topic/CMFCColorPickerCtrl::SetColor.md)|Définit la couleur actuelle à la valeur de couleur spécifiée RVB.|  
|[CMFCColorPickerCtrl::SetHLS](../Topic/CMFCColorPickerCtrl::SetHLS.md)|Définit la couleur actuelle à la valeur de couleur spécifiée de HLS.|  
|[CMFCColorPickerCtrl::SetHue](../Topic/CMFCColorPickerCtrl::SetHue.md)|Modifie le composant de tonalité de la couleur sélectionnée.|  
|[CMFCColorPickerCtrl::SetLuminance](../Topic/CMFCColorPickerCtrl::SetLuminance.md)|Modifie le composant de luminosité de la couleur sélectionnée.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](../Topic/CMFCColorPickerCtrl::SetLuminanceBarWidth.md)|Définit la largeur de la barre de luminosité dans le contrôle de sélecteur de couleurs.|  
|[CMFCColorPickerCtrl::SetOriginalColor](../Topic/CMFCColorPickerCtrl::SetOriginalColor.md)|Définit la couleur par défaut initiale.|  
|[CMFCColorPickerCtrl::SetPalette](../Topic/CMFCColorPickerCtrl::SetPalette.md)|Définit la palette couleurs actuelle.|  
|[CMFCColorPickerCtrl::SetSaturation](../Topic/CMFCColorPickerCtrl::SetSaturation.md)|Modifie le composant de saturation de la couleur sélectionnée.|  
|[CMFCColorPickerCtrl::SetType](../Topic/CMFCColorPickerCtrl::SetType.md)|Définit le type de contrôle de sélecteur de couleurs à afficher.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](../Topic/CMFCColorPickerCtrl::DrawCursor.md)|Appelé par l'infrastructure avant un curseur qui indique la couleur sélectionnée s'affiche.|  
  
## Notes  
 Les couleurs standard sont sélectionnées dans une palette de couleurs hexagonale, et les couleurs personnalisées sont activées d'une barre de luminosité où les couleurs sont spécifiées en utilisant l'une ou l'autre rouge et vert\/notation bleue ou notation de tonalité\/\/satuaration luminance.  
  
 l'illustration suivante représente plusieurs objets d' `CMFCColorPickerCtrl` .  
  
 ![Boîte de dialogue CMFCColorPickerCtrl](../../mfc/reference/media/colorpicker.png "ColorPicker")  
  
 `CMFCColorPickerCtrl` prend en charge deux paires de styles.  Les styles d'HEXA et de HEX\_GREYSCALE sont appropriés pour la sélection de couleurs standard.  Les styles de RÉCOLTEUSE et de LUMINOSITÉ sont appropriés pour la sélection de couleurs personnalisée.  
  
 Exécutez les étapes suivantes pour incorporer le contrôle d' `CMFCColorPickerCtrl` à votre boîte de dialogue :  
  
1.  Si vous utilisez **ClassWizard**, insérez un contrôle bouton dans votre modèle de boîte de dialogue \(car la classe d' `CMFCColorPickerCtrl` est héritée de la classe d' `CButton` \).  
  
2.  Insérez une variable membre qui est associée au contrôle bouton dans votre classe de boîte de dialogue.  Modifiez le type de variable d' `CButton` par `CMFCColorPickerCtrl`.  
  
3.  Insérez le gestionnaire de messages d' `WM_INITDIALOG` pour la classe de boîte de dialogue.  Dans le gestionnaire, définissez le type, la palette, et l'initial couleur sélectionnée du contrôle d' `CMFCColorPickerCtrl` .  
  
## Exemple  
 L'exemple suivant montre comment configurer un objet d' `CMFCColorPickerCtrl` en utilisant différentes méthodes dans la classe d' `CMFCColorPickerCtrl` .  L'exemple montre comment définir le type de contrôle picker, et comment définir sa couleur, tonalité, luminosité, et saturation.  l'exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/CPP/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/CPP/cmfccolorpickerctrl-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## Configuration requise  
 **en\-tête :** afxcolorpickerctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)