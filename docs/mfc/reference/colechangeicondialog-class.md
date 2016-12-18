---
title: "COleChangeIconDialog Class | Microsoft Docs"
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
  - "COleChangeIconDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Change Icon dialog box"
  - "COleChangeIconDialog class"
  - "boîtes de dialogue, OLE"
  - "OLE Change Icon dialog box"
  - "boîtes de dialogue OLE, Change Icon"
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleChangeIconDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour OLE boîte de dialogue d'icône de modification.  
  
## Syntaxe  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](../Topic/COleChangeIconDialog::COleChangeIconDialog.md)|Construit un objet `COleChangeIconDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](../Topic/COleChangeIconDialog::DoChangeIcon.md)|Exécute la modification spécifié de la boîte de dialogue.|  
|[COleChangeIconDialog::DoModal](../Topic/COleChangeIconDialog::DoModal.md)|Affiche la boîte de dialogue d'icône de modification OLE 2.|  
|[COleChangeIconDialog::GetIconicMetafile](../Topic/COleChangeIconDialog::GetIconicMetafile.md)|Obtient un handle vers le métafichier associé à la forme iconique de cet élément.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleChangeIconDialog::m\_ci](../Topic/COleChangeIconDialog::m_ci.md)|Une structure qui contrôle le comportement de la boîte de dialogue.|  
  
## Notes  
 Créez un objet de classe `COleChangeIconDialog` lorsque vous souhaitez appeler cette boîte de dialogue.  Après qu'un objet d' `COleChangeIconDialog` a été construit, vous pouvez utiliser la structure de [m\_ci](../Topic/COleChangeIconDialog::m_ci.md) pour initialiser les valeurs ou les états des contrôles dans la boîte de dialogue.  La structure d' `m_ci` est de type **OLEUICHANGEICON**.  Pour plus d'informations sur l'utilisation de cette classe de boîte de dialogue, consultez la fonction membre de [DoModal](../Topic/COleChangeIconDialog::DoModal.md) .  
  
 Pour plus d'informations, consultez la structure d' [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur les boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)