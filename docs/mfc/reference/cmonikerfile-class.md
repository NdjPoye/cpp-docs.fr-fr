---
title: "CMonikerFile Class | Microsoft Docs"
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
  - "CMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonikerFile class"
  - "IMoniker interface"
  - "IMoniker interface, liaison"
  - "monikers, MFC"
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMonikerFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un flux de données \([IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)\) nommées par [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## Syntaxe  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMonikerFile::CMonikerFile](../Topic/CMonikerFile::CMonikerFile.md)|Construit un objet `CMonikerFile`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMonikerFile::Close](../Topic/CMonikerFile::Close.md)|Détache et libère le flux et libère le moniker.|  
|[CMonikerFile::Detach](../Topic/CMonikerFile::Detach.md)|Détache `IMoniker` de cet objet d' `CMonikerFile` .|  
|[CMonikerFile::GetMoniker](../Topic/CMonikerFile::GetMoniker.md)|Retourne le moniker actuel.|  
|[CMonikerFile::Open](../Topic/CMonikerFile::Open.md)|Ouvre le fichier spécifié pour obtenir un flux.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMonikerFile::CreateBindContext](../Topic/CMonikerFile::CreateBindContext.md)|Obtient le contexte de liaison ou crée un contexte de liaison initialisé par défaut.|  
  
## Notes  
 Un moniker contient les informations de façon très similaire à un nom de chemin d'accès à un fichier.  Si vous avez un pointeur vers l'interface d' `IMoniker` d'un objet moniker, vous pouvez accéder au fichier marqué sans avoir toutes autres informations spécifiques sur lequel se trouve le fichier réellement.  
  
 Dérivé d' `COleStreamFile`, `CMonikerFile` prend un moniker ou une représentation sous forme de chaîne qu'il peut transformer en moniker et lie au flux de données pour lequel le moniker est un nom.  Vous pouvez ensuite lire et écrire dans le flux.  L'objectif réel d' `CMonikerFile` est de fournir l'accès simple à `IStream`s nommé par `IMoniker`s afin que vous n'ayez pas à lier à un flux vous\-même, mais possède des fonctionnalités d' `CFile` au flux.  
  
 `CMonikerFile` ne peut pas être utilisé pour le lier à une valeur autre qu'un flux.  Si vous souhaitez lier à la mémoire ou à un objet, vous devez utiliser l'interface d' `IMoniker` directement.  
  
 Pour plus d'informations sur les flux et les monikers, consultez [COleStreamFile](../../mfc/reference/colestreamfile-class.md) dans MFC *Reference* et [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) et l' [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [COleStreamFile Class](../../mfc/reference/colestreamfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)