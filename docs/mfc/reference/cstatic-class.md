---
title: "CStatic Class | Microsoft Docs"
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
  - "CStatic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitmaps, afficher"
  - "controls [MFC], statiques"
  - "CStatic class"
  - "curseurs, afficher"
  - "enhanced metafiles"
  - "enhanced metafiles, afficher"
  - "icônes, afficher"
  - "static controls"
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatic Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'un contrôle statique de windows.  
  
## Syntaxe  
  
```  
class CStatic : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStatic::CStatic](../Topic/CStatic::CStatic.md)|Construit un objet `CStatic`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStatic::Create](../Topic/CStatic::Create.md)|Crée le contrôle statique windows et l'attache à l'objet d' `CStatic` .|  
|[CStatic::DrawItem](../Topic/CStatic::DrawItem.md)|Substitution pour dessiner un contrôle statique owner\-drawn.|  
|[CStatic::GetBitmap](../Topic/CStatic::GetBitmap.md)|Récupère le handle de la bitmap précédemment définie avec [SetBitmap](../Topic/CStatic::SetBitmap.md).|  
|[CStatic::GetCursor](../Topic/CStatic::GetCursor.md)|Récupère le handle de l'image de curseur précédemment définie avec [SetCursor](../Topic/CStatic::SetCursor.md).|  
|[CStatic::GetEnhMetaFile](../Topic/CStatic::GetEnhMetaFile.md)|Récupère le handle de métafichier amélioré précédemment définie avec [SetEnhMetaFile](../Topic/CStatic::SetEnhMetaFile.md).|  
|[CStatic::GetIcon](../Topic/CStatic::GetIcon.md)|Récupère le handle de l'icône précédemment définie avec [SetIcon](../Topic/CStatic::SetIcon.md).|  
|[CStatic::SetBitmap](../Topic/CStatic::SetBitmap.md)|Spécifie une bitmap à afficher dans le contrôle statique.|  
|[CStatic::SetCursor](../Topic/CStatic::SetCursor.md)|Spécifie une image de curseur à afficher dans le contrôle statique.|  
|[CStatic::SetEnhMetaFile](../Topic/CStatic::SetEnhMetaFile.md)|Spécifie un métafichier amélioré à afficher dans le contrôle statique.|  
|[CStatic::SetIcon](../Topic/CStatic::SetIcon.md)|Spécifie une icône à afficher dans le contrôle statique.|  
  
## Notes  
 Un contrôle statique affiche une chaîne de texte, une zone, un rectangle, une icône, un curseur, une bitmap, ou un métafichier amélioré.  Il peut être utilisé pour étiqueter, boxing, ou séparer autres contrôles.  Un contrôle statique normalement n'effectue aucune entrée et ne fournit aucune sortie ; toutefois, il peut indiquer son parent les clics de souris s'il a créé avec le style de **SS\_NOTIFY** .  
  
 Créez un contrôle statique en deux étapes.  D'abord, appelez le constructeur pour construire l'objet d' `CStatic` , puis appelez la fonction membre de [Create](../Topic/CStatic::Create.md) pour créer le contrôle statique et le lier à l'objet d' `CStatic` .  
  
 Si vous créez un objet d' `CStatic` dans une boîte de dialogue \(via une ressource de boîte de dialogue\), l'objet d' `CStatic` est automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un objet d' `CStatic` dans une fenêtre, vous devrez peut\-être également la destruction.  Un objet d' `CStatic` créé sur la pile dans une fenêtre est automatiquement détruit.  Si vous créez l'objet d' `CStatic` sur le tas à l'aide de la fonction de **nouveau** , vous devez appeler **supprimer** sur l'objet pour le détruire lorsque vous avez terminé avec lui.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)