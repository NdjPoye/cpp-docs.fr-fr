---
title: "COleLinksDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinksDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinksDialog class"
  - "boîtes de dialogue, OLE"
  - "Edit Links dialog box"
  - "OLE Edit Links dialog box"
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleLinksDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour OLE modification joint la boîte de dialogue.  
  
## Syntaxe  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleLinksDialog::COleLinksDialog](../Topic/COleLinksDialog::COleLinksDialog.md)|Construit un objet `COleLinksDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleLinksDialog::DoModal](../Topic/COleLinksDialog::DoModal.md)|Affiche OLE boîte de dialogue de liens de modification.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleLinksDialog::m\_el](../Topic/COleLinksDialog::m_el.md)|Une structure de type **OLEUIEDITLINKS** qui contrôle le comportement de la boîte de dialogue.|  
  
## Notes  
 Créez un objet de classe `COleLinksDialog` lorsque vous souhaitez appeler cette boîte de dialogue.  Après qu'un objet d' `COleLinksDialog` a été construit, vous pouvez utiliser la structure de [m\_el](../Topic/COleLinksDialog::m_el.md) pour initialiser les valeurs ou les états des contrôles dans la boîte de dialogue.  La structure d' `m_el` est de type **OLEUIEDITLINKS**.  Pour plus d'informations sur l'utilisation de cette classe de boîte de dialogue, consultez la fonction membre de [DoModal](../Topic/COleLinksDialog::DoModal.md) .  
  
> [!NOTE]
>  Le code généré par l'Assistant de conteneur application utilise cette classe.  
  
 Pour plus d'informations, consultez la structure d' [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur des boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)