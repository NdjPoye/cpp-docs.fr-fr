---
title: "COleDataObject Class | Microsoft Docs"
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
  - "IDataObject"
  - "COleDataObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Presse-papiers (C++), MFC support"
  - "Presse-papiers (C++), OLE support"
  - "COleDataObject class"
  - "data transfer [C++]"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], MFC support"
  - "IDataObject interface, MFC encapsulation"
  - "OLE (C++), uniform data transfer"
  - "OLE Clipboard [C++], prise en charge"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé dans les transferts de données de récupération des données dans divers formats du presse\-papiers, via le glisser\-déplacer, ou d'un élément OLE incorporé.  
  
## Syntaxe  
  
```  
class COleDataObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDataObject::COleDataObject](../Topic/COleDataObject::COleDataObject.md)|Construit un objet `COleDataObject`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDataObject::Attach](../Topic/COleDataObject::Attach.md)|Joint le OLE objet de données spécifié à `COleDataObject`.|  
|[COleDataObject::AttachClipboard](../Topic/COleDataObject::AttachClipboard.md)|Joint l'objet de données qui est dans le presse\-papiers.|  
|[COleDataObject::BeginEnumFormats](../Topic/COleDataObject::BeginEnumFormats.md)|Se prépare à un ou plusieurs appels suivants d' `GetNextFormat` .|  
|[COleDataObject::Detach](../Topic/COleDataObject::Detach.md)|Détache l'objet associé à `IDataObject` .|  
|[COleDataObject::GetData](../Topic/COleDataObject::GetData.md)|Copie des données du OLE objet de données lié dans un format spécifié.|  
|[COleDataObject::GetFileData](../Topic/COleDataObject::GetFileData.md)|Copie des données du OLE objet de données lié dans un pointeur d' `CFile` dans le format spécifié.|  
|[COleDataObject::GetGlobalData](../Topic/COleDataObject::GetGlobalData.md)|Copie des données du OLE objet de données lié dans `HGLOBAL` dans le format spécifié.|  
|[COleDataObject::GetNextFormat](../Topic/COleDataObject::GetNextFormat.md)|Retourne le prochain format de données disponible.|  
|[COleDataObject::IsDataAvailable](../Topic/COleDataObject::IsDataAvailable.md)|Vérifie si les données sont disponibles dans un format spécifié.|  
|[COleDataObject::Release](../Topic/COleDataObject::Release.md)|Détache et libère l'objet associé à `IDataObject` .|  
  
## Notes  
 `COleDataObject` n'a pas de classe de base.  
  
 Ces types de transferts de données incluent une source et de destination.  La source de données est implémentée comme objet de la classe de [COleDataSource](../../mfc/reference/coledatasource-class.md) .  Chaque fois qu'une application de destination contient des données déplacées dans celle\-ci ou est appelée sur pour exécuter une opération de coller du presse\-papiers, un objet de la classe d' `COleDataObject` doit être créé.  
  
 Cette classe vous permet de déterminer si les données existent dans un format spécifié.  Vous pouvez également énumérer les formats de données disponibles ou le contrôle si un format spécifié est disponible puis extraire les données du format par défaut.  La recherche de l'objet peut être effectuée de différentes façons, notamment l'utilisation de [fichier C](../../mfc/reference/cfile-class.md), d' `HGLOBAL`, ou d'une structure de **STGMEDIUM** .  
  
 Pour plus d'informations, consultez la structure de [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur l'utilisation des objets de données dans votre application, consultez l'article [Objets de données et sources de données \(\) OLE](../../mfc/data-objects-and-data-sources-ole.md).  
  
## Hiérarchie d'héritage  
 `COleDataObject`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDataSource Class](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [CView::OnDrop](../Topic/CView::OnDrop.md)