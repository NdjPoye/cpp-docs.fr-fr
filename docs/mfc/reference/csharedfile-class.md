---
title: "CSharedFile Class | Microsoft Docs"
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
  - "CSharedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSharedFile class"
  - "memory files"
  - "shared memory files"
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSharedFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CMemFile](../../mfc/reference/cmemfile-class.md)classe dérivée qui prend en charge des fichiers de mémoire partagée.  
  
## Syntaxe  
  
```  
class CSharedFile : public CMemFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSharedFile::CSharedFile](../Topic/CSharedFile::CSharedFile.md)|Construit un objet `CSharedFile`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSharedFile::Detach](../Topic/CSharedFile::Detach.md)|Ferme le fichier de mémoire partagée et retourne le handle de son bloc de mémoire.|  
|[CSharedFile::SetHandle](../Topic/CSharedFile::SetHandle.md)|Joint le fichier de mémoire partagée à un bloc de mémoire.|  
  
## Notes  
 Les fichiers magasin se comportent comme des fichiers sur disque mais que le fichier est stocké dans la mémoire vive plutôt que sur le disque.  Un fichier de stockage est utile pour le stockage temporaire rapide ou pour transférer des octets bruts ou des objets sérialisés entre les processus indépendants.  
  
 Les fichiers de mémoire partagée diffèrent d'autres fichiers de mémoire dans cette mémoire pour eux est alloué avec la fonction Windows de [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) .  La classe d' `CSharedFile` stocke des données dans un bloc de mémoire alloué de façon globale \(créé à l'aide de **GlobalAlloc**\), et ce bloc de mémoire peut être partagé avec DDE, le presse\-papiers, ou d'autres opérations de transfert de données uniformes d'OLE\/COM, par exemple, l'utilisation `IDataObject`.  
  
 **GlobalAlloc** retourne un handle d' `HGLOBAL` plutôt qu'un pointeur vers la mémoire, telle que le pointeur retourné par [malloc](../../c-runtime-library/reference/malloc.md).  Le handle d' `HGLOBAL` est nécessaire dans certaines applications.  Par exemple, pour placer des données dans le presse\-papiers vous avez besoin d'un handle d' `HGLOBAL` .  
  
 Notez qu' `CSharedFile` n'utilise pas les fichiers mappés en mémoire, et les données ne peuvent pas être directement partagées entre les processus.  
  
 Les objets d'`CSharedFile` peuvent automatiquement allouer leur propre mémoire ou vous pouvez attacher votre propre bloc de mémoire à l'objet d' `CSharedFile` en appelant [CSharedFile::SetHandle](../Topic/CSharedFile::SetHandle.md).  Dans l'un ou l'autre de point de droite, la mémoire pour élever le fichier de mémoire automatiquement est allouée par incréments de taille d' `nGrowBytes`si `nGrowBytes` n'est pas nul.  
  
 Pour plus d'informations, consultez l'article [fichiers dans MFC](../../mfc/files-in-mfc.md) et [gestion de fichiers](../../c-runtime-library/file-handling.md) dans *la référence de la bibliothèque Runtime*.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## Configuration requise  
 **Header:** afxadv.h  
  
## Voir aussi  
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)   
 [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)   
 [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)