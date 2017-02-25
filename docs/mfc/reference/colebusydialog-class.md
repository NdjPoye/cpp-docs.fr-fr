---
title: "COleBusyDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleBusyDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleBusyDialog class"
  - "Server Busy dialog box"
  - "Server Not Responding dialog box"
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleBusyDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour le serveur OLE boîtes de dialogue occupées de réponse ou serveur.  
  
## Syntaxe  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleBusyDialog::COleBusyDialog](../Topic/COleBusyDialog::COleBusyDialog.md)|Construit un objet `COleBusyDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleBusyDialog::DoModal](../Topic/COleBusyDialog::DoModal.md)|Affiche la boîte de dialogue occupée de OLE serveur.|  
|[COleBusyDialog::GetSelectionType](../Topic/COleBusyDialog::GetSelectionType.md)|Détermine le tableau fait dans la boîte de dialogue.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleBusyDialog::m\_bz](../Topic/COleBusyDialog::m_bz.md)|Structure du type **OLEUIBUSY** qui contrôle le comportement de la boîte de dialogue.|  
  
## Notes  
 Créez un objet de classe `COleBusyDialog` lorsque vous souhaitez appeler ces boîtes de dialogue.  Après qu'un objet d' `COleBusyDialog` a été construit, vous pouvez utiliser la structure de [m\_bz](../Topic/COleBusyDialog::m_bz.md) pour initialiser les valeurs ou les états des contrôles dans la boîte de dialogue.  La structure d' `m_bz` est de type **OLEUIBUSY**.  Pour plus d'informations sur l'utilisation de cette classe de boîte de dialogue, consultez la fonction membre de [DoModal](../Topic/COleBusyDialog::DoModal.md) .  
  
> [!NOTE]
>  Le code généré par l'Assistant de conteneur application utilise cette classe.  
  
 Pour plus d'informations, consultez la structure d' [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur les boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)