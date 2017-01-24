---
title: "CAsyncMonikerFile Class | Microsoft Docs"
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
  - "CAsyncMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), asynchrones"
  - "asynchronous controls [C++]"
  - "CAsyncMonikerFile class"
  - "IMoniker interface, liaison"
  - "monikers [C++], MFC"
  - "contrôles OLE (C++), asynchrones"
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAsyncMonikerFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités pour l'utilisation des monikers asynchrones dans les contrôles ActiveX \(précédemment OLE contrôles\).  
  
## Syntaxe  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](../Topic/CAsyncMonikerFile::CAsyncMonikerFile.md)|Construit un objet `CAsyncMonikerFile`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncMonikerFile::Close](../Topic/CAsyncMonikerFile::Close.md)|Ferme et libère toutes les ressources.|  
|[CAsyncMonikerFile::GetBinding](../Topic/CAsyncMonikerFile::GetBinding.md)|Extrait un pointeur vers la liaison de migration asynchrone.|  
|[CAsyncMonikerFile::GetFormatEtc](../Topic/CAsyncMonikerFile::GetFormatEtc.md)|Récupère le format des données dans le flux.|  
|[CAsyncMonikerFile::Open](../Topic/CAsyncMonikerFile::Open.md)|Ouvre un fichier de façon asynchrone.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](../Topic/CAsyncMonikerFile::CreateBindStatusCallback.md)|Crée un objet COM qui implémente `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](../Topic/CAsyncMonikerFile::GetBindInfo.md)|Appelé par OLE bibliothèque système pour demander des informations sur le type de liaison à créer.|  
|[CAsyncMonikerFile::GetPriority](../Topic/CAsyncMonikerFile::GetPriority.md)|Appelé par OLE bibliothèque système pour obtenir la priorité de la liaison.|  
|[CAsyncMonikerFile::OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md)|Appelé pour fournir des données comme elle devient disponible au client pendant les opérations de liaison asynchrones.|  
|[CAsyncMonikerFile::OnLowResource](../Topic/CAsyncMonikerFile::OnLowResource.md)|Appelée lorsque les ressources sont insuffisantes.|  
|[CAsyncMonikerFile::OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md)|Appelé pour indiquer la progression dans le processus de téléchargement de données.|  
|[CAsyncMonikerFile::OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md)|Appelé lorsque la liaison démarre.|  
|[CAsyncMonikerFile::OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md)|Appelé lorsque le transfert asynchrone est arrêté.|  
  
## Notes  
 Dérivé de [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), qui à son tour est dérivé de [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` utilise l'interface d' [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) pour accéder à n'importe quel flux de données de façon asynchrone, notamment les fichiers de charge de manière asynchrone à partir d'une URL.  Les fichiers peuvent être des propriétés de datapath des contrôles ActiveX.  
  
 Les monikers asynchrones sont principalement utilisés dans des applications activées pour Internet et des contrôles ActiveX de fournir une interface utilisateur réactif pendant les transferts de fichiers.  Un exemple typique de cela est l'utilisation de [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) de fournir des propriétés asynchrones pour les contrôles ActiveX.  L'objet d' `CDataPathProperty` obtiendra à plusieurs reprises un rappel pour indiquer la disponibilité de nouvelles données pendant un processus long d'échange de propriétés.  
  
 Pour plus d'informations sur l'utilisation des monikers asynchrones et des contrôles ActiveX dans les applications Web, consultez les articles suivants :  
  
-   [Premières étapes Internet : monikers asynchrones](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Premières étapes Internet : Contrôles ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [Asynchronous Versus Synchronous Monikers](http://msdn.microsoft.com/library/windows/desktop/ms687193)