---
title: "COleDataSource Class | Microsoft Docs"
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
  - "COleDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Presse-papiers (C++), MFC support"
  - "Presse-papiers (C++), OLE support"
  - "COleDataSource class"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], MFC support"
  - "IDataObject, MFC encapsulation"
  - "OLE (C++), uniform data transfer"
  - "OLE Clipboard [C++], prise en charge"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Agit comme un cache dans lequel une application définit les données qu'elle offrira pendant les opérations de transfert de données, telles que le presse\-papiers ou les opérations de glisser\-déplacer.  
  
## Syntaxe  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDataSource::COleDataSource](../Topic/COleDataSource::COleDataSource.md)|Construit un objet `COleDataSource`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDataSource::CacheData](../Topic/COleDataSource::CacheData.md)|Offre des données dans un format spécifié à l'aide d'une structure de **STGMEDIUM** .|  
|[COleDataSource::CacheGlobalData](../Topic/COleDataSource::CacheGlobalData.md)|Offre des données dans un format spécifié à `HGLOBAL`.|  
|[COleDataSource::DelayRenderData](../Topic/COleDataSource::DelayRenderData.md)|Offre des données dans un format spécifié à l'aide de le rendu différé.|  
|[COleDataSource::DelayRenderFileData](../Topic/COleDataSource::DelayRenderFileData.md)|Offre des données dans un format spécifié dans un pointeur d' `CFile` .|  
|[COleDataSource::DelaySetData](../Topic/COleDataSource::DelaySetData.md)|Appelé pour chaque format qui est pris en charge dans `OnSetData`.|  
|[COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)|Exécute les opérations glisser\-déplacer avec une source de données.|  
|[COleDataSource::Empty](../Topic/COleDataSource::Empty.md)|Vide l'objet d' `COleDataSource` des données.|  
|[COleDataSource::FlushClipboard](../Topic/COleDataSource::FlushClipboard.md)|Affiche toutes les données dans le presse\-papiers.|  
|[COleDataSource::GetClipboardOwner](../Topic/COleDataSource::GetClipboardOwner.md)|Vérifie que les données placées dans le presse\-papiers sont toujours présents.|  
|[COleDataSource::OnRenderData](../Topic/COleDataSource::OnRenderData.md)|Récupère les données dans le cadre de le rendu différé.|  
|[COleDataSource::OnRenderFileData](../Topic/COleDataSource::OnRenderFileData.md)|Récupère les données dans `CFile` dans le cadre de le rendu différé.|  
|[COleDataSource::OnRenderGlobalData](../Topic/COleDataSource::OnRenderGlobalData.md)|Récupère les données dans `HGLOBAL` dans le cadre de le rendu différé.|  
|[COleDataSource::OnSetData](../Topic/COleDataSource::OnSetData.md)|Appelé pour remplacer les données dans `COleDataSource` objet.|  
|[COleDataSource::SetClipboard](../Topic/COleDataSource::SetClipboard.md)|Définit un objet d' `COleDataSource` dans le presse\-papiers.|  
  
## Notes  
 Vous pouvez créer OLE de sources de données directement.  Sinon, les classes de [COleClientItem](../../mfc/reference/coleclientitem-class.md) et de [COleServerItem](../../mfc/reference/coleserveritem-class.md) créent OLE de sources de données en réponse à leurs fonctions membres d' `CopyToClipboard` et d' `DoDragDrop` .  Consultez [COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md) pour une brève description.  Substituez la fonction membre d' `OnGetClipboardData` de votre classe d'élément client ou d'élément du serveur pour ajouter des formats de presse\-papiers supplémentaires aux données dans OLE source de données créée pour la fonction membre d' `CopyToClipboard` ou d' `DoDragDrop` .  
  
 Chaque fois que vous voulez préparer des données d'un transfert, vous devez créer un objet de cette classe et le remplissage de vos données à l'aide de la plupart de méthode correspondant à vos données.  La façon dont il est inséré dans une source de données est directement affectée par si les données sont fournies immédiatement \(rendu immédiat\) ou à la demande \(rendu différée\).  Pour chaque format de presse\-papiers dans lequel vous fournissez des données en passant le format de presse\-papiers à utiliser \(\) et une structure facultative de [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) \), appelez [DelayRenderData](../Topic/COleDataSource::DelayRenderData.md).  
  
 Pour plus d'informations sur les sources de données et le transfert de données, consultez l'article [Objets de données et sources de données \(\) OLE](../../mfc/data-objects-and-data-sources-ole.md).  En outre, l'article [Rubriques du presse\-papiers](../../mfc/clipboard.md) décrit le mécanisme de presse\-papiers OLE.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDataObject Class](../../mfc/reference/coledataobject-class.md)