---
title: "CCachedDataPathProperty Class | Microsoft Docs"
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
  - "CCachedDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), asynchrones"
  - "asynchronous controls [C++]"
  - "CCachedDataPathProperty class"
  - "memory files [C++]"
  - "contrôles OLE (C++), asynchrones"
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCachedDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une propriété de contrôle OLE transférée de façon asynchrone et mise en cache dans un fichier de mémoire.  
  
## Syntaxe  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](../Topic/CCachedDataPathProperty::CCachedDataPathProperty.md)|Construit un objet `CCachedDataPathProperty`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCachedDataPathProperty::m\_Cache](../Topic/CCachedDataPathProperty::m_Cache.md)|Objet d'`CMemFile` dans lequel pour mettre en cache des données.|  
  
## Notes  
 Un fichier de stockage est stocké dans la mémoire vive plutôt que sur le disque et est utile pour les transferts temporaires rapides.  
  
 Avec **CAysncMonikerFile** et `CDataPathProperty`, `CCachedDataPathProperty` fournit les fonctionnalités pour l'utilisation des monikers asynchrones dans les contrôles OLE.  Avec les objets d' `CCachedDataPathProperty` , vous pouvez transférer des données de manière asynchrone à partir d'une source d'URL ou de fichier et les stocker dans un fichier de mémoire via la variable publiques d' `m_Cache` .  Toutes les données sont stockées dans le fichier de mémoire, et il n'est pas nécessaire de substituer [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) sauf si vous souhaitez surveiller des notifications et répondre.  Par exemple, si vous transférez un fichier de .GIF et souhaitez avertir votre contrôle que davantage de données sont archivées et elles doivent se repeindre, substitution `OnDataAvailable` pour que la notification.  
  
 La classe `CCachedDataPathProperty` est dérivée d' `CDataPathProperty`.  
  
 Pour plus d'informations sur l'utilisation des monikers asynchrones et des contrôles ActiveX dans les applications Web, consultez les rubriques suivantes :  
  
-   [Premières étapes Internet : Contrôles ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
-   [Premières étapes Internet : monikers asynchrones](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)