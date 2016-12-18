---
title: "COleStreamFile Class | Microsoft Docs"
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
  - "COleStreamFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleStreamFile class"
  - "data streams [C++]"
  - "data streams [C++], OLE"
  - "OLE (C++), streams of data"
  - "OLE structured storage [C++]"
  - "streams [C++], OLE"
  - "structured storage in OLE"
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleStreamFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un flux de données \(`IStream`\) dans un fichier composé dans le cadre de OLE est structuré la mémoire.  
  
## Syntaxe  
  
```  
class COleStreamFile : public CFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleStreamFile::COleStreamFile](../Topic/COleStreamFile::COleStreamFile.md)|Construit un objet `COleStreamFile`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleStreamFile::Attach](../Topic/COleStreamFile::Attach.md)|Associe un flux à l'objet.|  
|[COleStreamFile::CreateMemoryStream](../Topic/COleStreamFile::CreateMemoryStream.md)|Crée un flux de mémoire globale et l'associe à l'objet.|  
|[COleStreamFile::CreateStream](../Topic/COleStreamFile::CreateStream.md)|Crée un flux et l'associe à l'objet.|  
|[COleStreamFile::Detach](../Topic/COleStreamFile::Detach.md)|Dissocie le flux de l'objet.|  
|[COleStreamFile::GetStream](../Topic/COleStreamFile::GetStream.md)|Retourne le flux actuel.|  
|[COleStreamFile::OpenStream](../Topic/COleStreamFile::OpenStream.md)|Ouvre sans risque un flux et l'associe à l'objet.|  
  
## Notes  
 Un objet d' `IStorage` doit exister pour que le flux peut être ouvert ou créé à moins qu'il soit un flux de mémoire.  
  
 Les objets d'`COleStreamFile` sont manipulés exactement comme des objets de [fichier C](../../mfc/reference/cfile-class.md) .  
  
 Pour plus d'informations sur la manipulation des flux et les magasins, consultez l'article. [conteneurs : fichiers composés](../../mfc/containers-compound-files.md).  
  
 Pour plus d'informations, consultez [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) et l' [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)