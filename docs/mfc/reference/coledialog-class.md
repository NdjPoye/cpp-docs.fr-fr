---
title: "COleDialog Class | Microsoft Docs"
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
  - "COleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDialog class"
  - "boîtes de dialogue, OLE"
  - "boîtes de dialogue OLE, classe de base"
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit des fonctionnalités communes à des boîtes de dialogue pour OLE.  
  
## Syntaxe  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDialog::GetLastError](../Topic/COleDialog::GetLastError.md)|Obtient un code d'erreur retourné par la boîte de dialogue.|  
  
## Notes  
 La bibliothèque MFC fournit plusieurs classes dérivées d' `COleDialog`:  
  
-   [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)  
  
-   [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)  
  
-   [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)  
  
-   [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
-   [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
-   [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)  
  
-   [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)  
  
-   [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)  
  
-   [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)  
  
 Pour plus d'informations sur les boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)