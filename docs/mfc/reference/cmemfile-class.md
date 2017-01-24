---
title: "CMemFile Class | Microsoft Docs"
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
  - "CMemFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemFile class"
  - "memory files"
  - "temporary files, memory files"
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMemFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[fichier C](../../mfc/reference/cfile-class.md)classe dérivée qui prend en charge des fichiers de mémoire.  
  
## Syntaxe  
  
```  
class CMemFile : public CFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMemFile::CMemFile](../Topic/CMemFile::CMemFile.md)|Crée un fichier objet de mémoire.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMemFile::Attach](../Topic/CMemFile::Attach.md)|Joint un bloc de mémoire à `CMemFile`.|  
|[CMemFile::Detach](../Topic/CMemFile::Detach.md)|Détache le bloc de mémoire d' `CMemFile` et retourne un pointeur vers le bloc de mémoire détaché.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMemFile::Alloc](../Topic/CMemFile::Alloc.md)|Substitution pour modifier le comportement d'allocation de mémoire.|  
|[CMemFile::Free](../Topic/CMemFile::Free.md)|Substitution pour modifier le comportement de désallocation de mémoire.|  
|[CMemFile::GrowFile](../Topic/CMemFile::GrowFile.md)|Substitution pour modifier le comportement en élevant un fichier.|  
|[CMemFile::Memcpy](../Topic/CMemFile::Memcpy.md)|Substitution pour modifier le comportement de copie de mémoire en lecture et en écriture des fichiers.|  
|[CMemFile::Realloc](../Topic/CMemFile::Realloc.md)|Substitution pour modifier le comportement de redistribution de mémoire.|  
  
## Notes  
 Ces fichiers de mémoire se comportent comme des fichiers sur disque mais que le fichier est stocké dans la mémoire vive plutôt que sur le disque.  Un fichier de stockage est utile pour le stockage temporaire rapide ou pour transférer des octets bruts ou des objets sérialisés entre les processus indépendants.  
  
 Les objets d'`CMemFile` peuvent automatiquement allouer leur propre mémoire ou vous pouvez attacher votre propre bloc de mémoire à l'objet d' `CMemFile` en appelant [Attachement](../Topic/CMemFile::Attach.md).  Dans l'un ou l'autre de point de droite, la mémoire pour élever le fichier de mémoire automatiquement est allouée par incréments de taille d' `nGrowBytes`si `nGrowBytes` n'est pas nul.  
  
 Le bloc de mémoire sera automatiquement supprimé lors de destruction de l'objet d' `CMemFile` si la mémoire était initialement allouée par l'objet d' `CMemFile` ; sinon, vous êtes chargé de libérer la mémoire que vous avez jointe à l'objet.  
  
 Vous pouvez accéder au bloc de mémoire via le pointeur fourni lorsque vous détachez le de l'objet d' `CMemFile` en appelant [détachez](../Topic/CMemFile::Detach.md).  
  
 L'utilisation la plus courante d' `CMemFile` consiste à créer un objet d' `CMemFile` et de l'utiliser en appelant les fonctions membres de [fichier C](../../mfc/reference/cfile-class.md) .  Notez que crée `CMemFile` l'ouvre automatiquement : vous n'appelez pas [CFile::Open](../Topic/CFile::Open.md), qui est utilisé uniquement pour des fichiers sur disque.  Étant donné qu' `CMemFile` n'utilise pas de fichier sur disque, le membre `CFile::m_hFile` n'est pas utilisée et n'a aucune signification.  
  
 Les fonctions membres d' `CFile`[double](../Topic/CFile::Duplicate.md), [LockRange](../Topic/CFile::LockRange.md), et [UnlockRange](../Topic/CFile::UnlockRange.md) ne sont pas implémentées pour `CMemFile`.  Si vous appelez ces fonctions sur `CMemFile` objet, obtiendront vous [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile` utilise les fonctions de la bibliothèque Runtime [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md), et [inscription](../../c-runtime-library/reference/free.md) pour allouer, réaffecter, et libérer la mémoire ; et l'intrinsèque [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) pour bloquer la mémoire de copie en lecture et en écriture.  Si vous souhaitez modifier ce comportement ou le comportement lorsque `CMemFile` élève un fichier, dérivez votre propre classe d' `CMemFile` et substituez les fonctions appropriées.  
  
 Pour plus d'informations sur `CMemFile`, consultez les articles [fichiers dans MFC](../../mfc/files-in-mfc.md) et [gestion de la mémoire \(MFC\)](../../mfc/memory-management.md) et voir le [gestion de fichiers](../../c-runtime-library/file-handling.md) dans *la référence de la bibliothèque Runtime*.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)