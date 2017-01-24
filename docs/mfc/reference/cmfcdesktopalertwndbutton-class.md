---
title: "CMFCDesktopAlertWndButton Class | Microsoft Docs"
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
  - "CMFCDesktopAlertWndButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndButton class"
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWndButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet des boutons à ajouter à une boîte de dialogue d'alerte sur le Bureau.  
  
## Syntaxe  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Constructeur par défaut.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Destructor.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](../Topic/CMFCDesktopAlertWndButton::IsCaptionButton.md)|Détermine si le bouton est affiché dans la zone de légende de la boîte de dialogue d'alerte.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](../Topic/CMFCDesktopAlertWndButton::IsCloseButton.md)|Détermine si le bouton ferme la boîte de dialogue d'alerte.|  
  
### Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Valeur booléenne qui spécifie si le bouton est affiché dans la zone de légende de la boîte de dialogue d'alerte.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Valeur booléenne qui spécifie si le bouton ferme la boîte de dialogue d'alerte.|  
  
### Remarques  
 Par défaut, le constructeur définit les données membres d' `m_bIsCaptionButton` et d' `m_bIsCloseButton` à `FALSE`.  Les jeux d'objets parents `m_bIsCaptionButton` d' `CMFCDesktopAlertDialog` à `TRUE` si le bouton est positionné dans la zone de légende de la boîte de dialogue d'alerte.  La classe d' `CMFCDesktopAlertDialog` crée un objet d' `CMFCDesktopAlertWndButton` qui sert de bouton qui ferme la boîte de dialogue d'alerte et définit `m_bIsCloseButton` à `TRUE`.  
  
 Ajoutez les objets d' `CMFCDesktopAlertWndButton` à un objet d' `CMFCDesktopAlertDialog` comme vous ajouteriez n'importe quel bouton.  Pour plus d'informations sur `CMFCDesktopAlertDialog`, consultez [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser la méthode d' `SetImage` dans la classe d' `CMFCDesktopAlertWndButton` .  Cet extrait de code fait partie d' [Exemple d'alerte de démonstration de Bureau](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxdesktopalertwnd.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)