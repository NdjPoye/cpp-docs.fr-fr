---
title: "CDataPathProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), asynchrones"
  - "asynchronous controls [C++]"
  - "CDataPathProperty class"
  - "contrôles OLE (C++), asynchrones"
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une propriété de contrôle OLE qui peut être chargée de façon asynchrone.  
  
## Syntaxe  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDataPathProperty::CDataPathProperty](../Topic/CDataPathProperty::CDataPathProperty.md)|Construit un objet `CDataPathProperty`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDataPathProperty::GetControl](../Topic/CDataPathProperty::GetControl.md)|Récupère le contrôle OLE asynchrone associé à l'objet d' `CDataPathProperty` .|  
|[CDataPathProperty::GetPath](../Topic/CDataPathProperty::GetPath.md)|Récupère le chemin de la propriété.|  
|[CDataPathProperty::Open](../Topic/CDataPathProperty::Open.md)|Initialise le chargement de la propriété asynchrone pour le contrôle associé ActiveX \(OLE\).|  
|[CDataPathProperty::ResetData](../Topic/CDataPathProperty::ResetData.md)|Appelle `CAsyncMonikerFile::OnDataAvailable` pour informer le conteneur que les propriétés du contrôle ont changé.|  
|[CDataPathProperty::SetControl](../Topic/CDataPathProperty::SetControl.md)|Définit le contrôle asynchrone ActiveX \(OLE\) associé à la propriété.|  
|[CDataPathProperty::SetPath](../Topic/CDataPathProperty::SetPath.md)|Définit le nom de chemin d'accès de la propriété.|  
  
## Notes  
 Les propriétés asynchrones sont chargés après l'initiation synchrone.  
  
 La classe `CDataPathProperty` est dérivée de **CAysncMonikerFile**.  Pour implémenter des propriétés asynchrones dans vos contrôles OLE, dérivez une classe d' `CDataPathProperty`, et remplacez [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md).  
  
 Pour plus d'informations sur l'utilisation des monikers asynchrones et des contrôles ActiveX dans les applications Web, consultez les articles suivants :  
  
-   [Premières étapes Internet : Contrôles ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
-   [Premières étapes Internet : monikers asynchrones](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [Image de l'exemple MFC](../../top/visual-cpp-samples.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)