---
title: "COleInsertDialog Class | Microsoft Docs"
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
  - "COleInsertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleInsertDialog class"
  - "boîtes de dialogue, OLE"
  - "Insert Object dialog box"
  - "OLE Insert Object dialog box"
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleInsertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour OLE boîte de dialogue d'objet d'insertion.  
  
## Syntaxe  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleInsertDialog::COleInsertDialog](../Topic/COleInsertDialog::COleInsertDialog.md)|Construit un objet `COleInsertDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleInsertDialog::CreateItem](../Topic/COleInsertDialog::CreateItem.md)|Crée l'élément sélectionné dans la boîte de dialogue.|  
|[COleInsertDialog::DoModal](../Topic/COleInsertDialog::DoModal.md)|Affiche OLE boîte de dialogue d'objet d'insertion.|  
|[COleInsertDialog::GetClassID](../Topic/COleInsertDialog::GetClassID.md)|Obtient **CLSID** associé à l'élément sélectionnez.|  
|[COleInsertDialog::GetDrawAspect](../Topic/COleInsertDialog::GetDrawAspect.md)|Indique si dessiner l'élément en tant qu'icône.|  
|[COleInsertDialog::GetIconicMetafile](../Topic/COleInsertDialog::GetIconicMetafile.md)|Obtient un handle vers le métafichier associé à la forme iconique de cet élément.|  
|[COleInsertDialog::GetPathName](../Topic/COleInsertDialog::GetPathName.md)|Obtient le chemin d'accès complet au fichier sélectionnez dans la boîte de dialogue.|  
|[COleInsertDialog::GetSelectionType](../Topic/COleInsertDialog::GetSelectionType.md)|Obtient le type d'objet sélectionné.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleInsertDialog::m\_io](../Topic/COleInsertDialog::m_io.md)|Une structure de type **OLEUIINSERTOBJECT** qui contrôle le comportement de la boîte de dialogue.|  
  
## Notes  
 Créez un objet de classe `COleInsertDialog` lorsque vous souhaitez appeler cette boîte de dialogue.  Après qu'un objet d' `COleInsertDialog` a été construit, vous pouvez utiliser la structure de [m\_io](../Topic/COleInsertDialog::m_io.md) pour initialiser les valeurs ou les états des contrôles dans la boîte de dialogue.  La structure d' `m_io` est de type **OLEUIINSERTOBJECT**.  Pour plus d'informations sur l'utilisation de cette classe de boîte de dialogue, consultez la fonction membre de [DoModal](../Topic/COleInsertDialog::DoModal.md) .  
  
> [!NOTE]
>  Le code généré par l'Assistant de conteneur application utilise cette classe.  
  
 Pour plus d'informations, consultez la structure d' [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur des boîtes de dialogue d'OLE\- détails, consultez l'article [boîtes de dialogue dans OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## Configuration requise  
 **Header:** afxodlgs.h  
  
## Voir aussi  
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)