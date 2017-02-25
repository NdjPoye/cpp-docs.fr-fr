---
title: "COlePasteSpecialDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COlePasteSpecialDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePasteSpecialDialog class"
  - "boîtes de dialogue, Paste Special"
  - "OLE Paste Special dialog box"
  - "Paste Special dialog box"
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COlePasteSpecialDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour OLE boîte de dialogue de spécial de collage.  
  
## Syntaxe  
  
```  
  
class COlePasteSpecialDialog : public COleDialog  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](../Topic/COlePasteSpecialDialog::COlePasteSpecialDialog.md)|Construit un objet `COlePasteSpecialDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md)|Ajoute des formats personnalisés à la liste de formats que votre application peut coller.|  
|[COlePasteSpecialDialog::AddLinkEntry](../Topic/COlePasteSpecialDialog::AddLinkEntry.md)|Ajoute une nouvelle entrée à la liste de formats de presse\-papiers pris en charge.|  
|[COlePasteSpecialDialog::AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md)|Ajoute **CF\_BITMAP**, **CF\_DIB**, `CF_METAFILEPICT`et, éventuellement `CF_LINKSOURCE` à la liste de formats que votre application peut coller.|  
|[COlePasteSpecialDialog::CreateItem](../Topic/COlePasteSpecialDialog::CreateItem.md)|Crée l'élément dans le document conteneur au format spécifié.|  
|[COlePasteSpecialDialog::DoModal](../Topic/COlePasteSpecialDialog::DoModal.md)|Affiche OLE boîte de dialogue de spécial de collage.|  
|[COlePasteSpecialDialog::GetDrawAspect](../Topic/COlePasteSpecialDialog::GetDrawAspect.md)|Indique si dessiner l'élément en tant qu'icône ou pas.|  
|[COlePasteSpecialDialog::GetIconicMetafile](../Topic/COlePasteSpecialDialog::GetIconicMetafile.md)|Obtient un handle vers le métafichier associé à la forme iconique de cet élément.|  
|[COlePasteSpecialDialog::GetPasteIndex](../Topic/COlePasteSpecialDialog::GetPasteIndex.md)|Obtient l'index des options de collage disponibles qui a été choisi par l'utilisateur.|  
|[COlePasteSpecialDialog::GetSelectionType](../Topic/COlePasteSpecialDialog::GetSelectionType.md)|Obtient le type de sélection sélectionnez.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COlePasteSpecialDialog::m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md)|Une structure de type **OLEUIPASTESPECIAL** qui contrôle la fonction de la boîte de dialogue.|  
  
## Notes  
 Créez un objet de classe `COlePasteSpecialDialog` lorsque vous souhaitez appeler cette boîte de dialogue.  Après qu'un objet d' `COlePasteSpecialDialog` a été construit, vous pouvez utiliser les fonctions membres d' [AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md) et d' [AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md) pour ajouter des formats de presse\-papiers à la boîte de dialogue.  Vous pouvez également utiliser la structure de [m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md) pour initialiser les valeurs ou les états des contrôles dans la boîte de dialogue.  La structure d' `m_ps` est de type **OLEUIPASTESPECIAL**.  
  
 Pour plus d'informations, consultez la structure d' [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur des boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)