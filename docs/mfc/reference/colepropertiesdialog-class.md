---
title: "COlePropertiesDialog Class | Microsoft Docs"
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
  - "COlePropertiesDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertiesDialog class"
  - "boîtes de dialogue, OLE"
  - "Object Properties dialog box"
  - "OLE documents, modifier les propriétés"
  - "OLE Object Properties dialog box"
  - "pages de propriétés, OLE"
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COlePropertiesDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule la boîte de dialogue Propriétés communes d'objets OLE windows.  
  
## Syntaxe  
  
```  
  
class COlePropertiesDialog : public COleDialog  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](../Topic/COlePropertiesDialog::COlePropertiesDialog.md)|Construit un objet `COlePropertiesDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePropertiesDialog::DoModal](../Topic/COlePropertiesDialog::DoModal.md)|Affiche la boîte de dialogue et permet à l'utilisateur d'effectuer une sélection.|  
|[COlePropertiesDialog::OnApplyScale](../Topic/COlePropertiesDialog::OnApplyScale.md)|Appelé par l'infrastructure lorsque la mise à l'échelle de l'élément de document a changé.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePropertiesDialog::m\_gp](../Topic/COlePropertiesDialog::m_gp.md)|Une structure utilisée pour initialiser la page « générale » d'un objet d' `COlePropertiesDialog` .|  
|[COlePropertiesDialog::m\_lp](../Topic/COlePropertiesDialog::m_lp.md)|Une structure utilisée pour initialiser la page « lien » d'un objet d' `COlePropertiesDialog` .|  
|[COlePropertiesDialog::m\_op](../Topic/COlePropertiesDialog::m_op.md)|Une structure utilisée pour initialiser l'objet d' `COlePropertiesDialog` .|  
|[COlePropertiesDialog::m\_psh](../Topic/COlePropertiesDialog::m_psh.md)|Une structure utilisée pour ajouter des pages de propriétés personnalisées supplémentaires.|  
|[COlePropertiesDialog::m\_vp](../Topic/COlePropertiesDialog::m_vp.md)|Une structure utilisée pour personnaliser la page «  » vue d'un objet d' `COlePropertiesDialog` .|  
  
## Notes  
 Les boîtes de dialogue Propriétés communes d'objets OLE offrent un moyen simple d'afficher et de modifier les propriétés d'un élément OLE de document d'une manière cohérente avec les normes de windows.  Ces propriétés incluent, entre autres, les informations sur le fichier représenté par l'élément de document, options pour afficher la mise à l'échelle d'icône et d'image, et les informations sur le lien de l'élément \(si l'élément est attaché\).  
  
 Pour utiliser un objet d' `COlePropertiesDialog` , créez d'abord l'objet à l'aide de le constructeur d' `COlePropertiesDialog` .  Une fois la boîte de dialogue a été générée, appelez la fonction membre d' `DoModal` pour afficher la boîte de dialogue et permettre à l'utilisateur de modifier les propriétés de l'élément.  `DoModal` retourne si l'utilisateur a sélectionné OK \(**IDOK**\) ou le bouton cancel \(**IDCANCEL**\).  En plus de OK et un bouton Annuler, un bouton de l'application.  Lorsque l'utilisateur sélectionne appliquez, toutes les modifications apportées aux propriétés de l'élément de document sont appliquées à l'élément et son image est automatiquement mise à jour, mais reste active.  
  
 Le membre de [m\_psh](../Topic/COlePropertiesDialog::m_psh.md) est un pointeur vers une structure de **PROPSHEETHEADER** , et dans la plupart des cas vous n'aurez pas besoin d'y accéder de manière explicite.  Une exception est lorsque vous avez besoin des pages de propriétés supplémentaires au delà de le général par défaut, les pages s'affiche, et de lien.  Dans ce cas, vous pouvez modifier la donnée membre d' `m_psh` pour inclure vos pages personnalisées avant d'appeler la fonction membre d' `DoModal` .  
  
 Pour plus d'informations sur OLE de boîtes de dialogue, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [MFC exemple CIRC](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage Class](../../mfc/reference/cpropertypage-class.md)