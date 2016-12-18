---
title: "COleChangeSourceDialog Class | Microsoft Docs"
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
  - "COleChangeSourceDialog"
  - "OLEUICHANGESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleChangeSourceDialog class"
  - "boîtes de dialogue, OLE"
  - "OLE Change Source dialog box"
  - "boîtes de dialogue OLE, Change Source"
  - "OleUIChangeSource structure"
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleChangeSourceDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour OLE boîte de dialogue de source de modification.  
  
## Syntaxe  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](../Topic/COleChangeSourceDialog::COleChangeSourceDialog.md)|Construit un objet `COleChangeSourceDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleChangeSourceDialog::DoModal](../Topic/COleChangeSourceDialog::DoModal.md)|Affiche OLE boîte de dialogue de source de modification.|  
|[COleChangeSourceDialog::GetDisplayName](../Topic/COleChangeSourceDialog::GetDisplayName.md)|Obtient le nom complet complet de source.|  
|[COleChangeSourceDialog::GetFileName](../Topic/COleChangeSourceDialog::GetFileName.md)|Obtient le nom du fichier du nom de la source.|  
|[COleChangeSourceDialog::GetFromPrefix](../Topic/COleChangeSourceDialog::GetFromPrefix.md)|Obtient le préfixe de la source précédente.|  
|[COleChangeSourceDialog::GetItemName](../Topic/COleChangeSourceDialog::GetItemName.md)|Obtient le nom de l'élément du nom de la source.|  
|[COleChangeSourceDialog::GetToPrefix](../Topic/COleChangeSourceDialog::GetToPrefix.md)|Obtient le préfixe de la nouvelle source|  
|[COleChangeSourceDialog::IsValidSource](../Topic/COleChangeSourceDialog::IsValidSource.md)|Indique si la source est valide.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleChangeSourceDialog::m\_cs](../Topic/COleChangeSourceDialog::m_cs.md)|Une structure qui contrôle le comportement de la boîte de dialogue.|  
  
## Notes  
 Créez un objet de classe `COleChangeSourceDialog` lorsque vous souhaitez appeler cette boîte de dialogue.  Après qu'un objet d' `COleChangeSourceDialog` a été construit, vous pouvez utiliser la structure de [m\_cs](../Topic/COleChangeSourceDialog::m_cs.md) pour initialiser les valeurs ou les états des contrôles dans la boîte de dialogue.  La structure d' `m_cs` est de type [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  Pour plus d'informations sur l'utilisation de cette classe de boîte de dialogue, consultez la fonction membre de [DoModal](../Topic/COleChangeSourceDialog::DoModal.md) .  
  
 Pour plus d'informations, consultez la structure d' [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur les boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)