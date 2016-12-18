---
title: "COleConvertDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleConvertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleConvertDialog class"
  - "Convertir (boîte de dialogue)"
  - "boîtes de dialogue, OLE"
  - "OLE Convert dialog box"
  - "boîtes de dialogue OLE, Convert"
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleConvertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour plus d'informations, consultez la structure d' [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Syntaxe  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleConvertDialog::COleConvertDialog](../Topic/COleConvertDialog::COleConvertDialog.md)|Construit un objet `COleConvertDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleConvertDialog::DoConvert](../Topic/COleConvertDialog::DoConvert.md)|Exécute la conversion spécifiée dans la boîte de dialogue.|  
|[COleConvertDialog::DoModal](../Topic/COleConvertDialog::DoModal.md)|Affiche OLE boîte de dialogue d'élément de modification.|  
|[COleConvertDialog::GetClassID](../Topic/COleConvertDialog::GetClassID.md)|Obtient **CLSID** associé à l'élément sélectionnez.|  
|[COleConvertDialog::GetDrawAspect](../Topic/COleConvertDialog::GetDrawAspect.md)|Spécifie si dessiner l'élément en tant qu'icône.|  
|[COleConvertDialog::GetIconicMetafile](../Topic/COleConvertDialog::GetIconicMetafile.md)|Obtient un handle vers le métafichier associé à la forme iconique de cet élément.|  
|[COleConvertDialog::GetSelectionType](../Topic/COleConvertDialog::GetSelectionType.md)|Obtient le type de sélection sélectionnez.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleConvertDialog::m\_cv](../Topic/COleConvertDialog::m_cv.md)|Une structure qui contrôle le comportement de la boîte de dialogue.|  
  
## Notes  
  
> [!NOTE]
>  Le code généré par l'Assistant de conteneur application utilise cette classe.  
  
 Pour plus d'informations sur les boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)