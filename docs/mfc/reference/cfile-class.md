---
title: "CFile Class | Microsoft Docs"
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
  - "CFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class, using with CFile"
  - "CFile class"
  - "fichiers (C++), classes for"
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base pour les classes de fichier Microsoft Foundation Class\).  
  
## Syntaxe  
  
```  
class CFile : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFile::CFile](../Topic/CFile::CFile.md)|Construit un objet d' `CFile` d'un chemin d'accès ou d'un handle de fichier.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFile::Abort](../Topic/CFile::Abort.md)|Ferme un fichier en ignorant les avertissements et erreurs.|  
|[CFile::Close](../Topic/CFile::Close.md)|Ferme un fichier et supprime l'objet.|  
|[CFile::Duplicate](../Topic/CFile::Duplicate.md)|Crée un objet en double\-cliquez sur ce fichier.|  
|[CFile::Flush](../Topic/CFile::Flush.md)|Vide toutes les données à écrire encore.|  
|[CFile::GetFileName](../Topic/CFile::GetFileName.md)|Récupère le nom de fichier du fichier sélectionné.|  
|[CFile::GetFilePath](../Topic/CFile::GetFilePath.md)|Récupère le chemin d'accès complet du fichier sélectionné.|  
|[CFile::GetFileTitle](../Topic/CFile::GetFileTitle.md)|Récupère le titre du fichier sélectionné.|  
|[CFile::GetLength](../Topic/CFile::GetLength.md)|Extrait la longueur du fichier.|  
|[CFile::GetPosition](../Topic/CFile::GetPosition.md)|Récupère le pointeur de fichier en cours.|  
|[CFile::GetStatus](../Topic/CFile::GetStatus.md)|Récupère le mode du fichier ouvert, ou dans la version statique, récupère l'état du fichier spécifié \(statique, fonction virtuelle\).|  
|[CFile::LockRange](../Topic/CFile::LockRange.md)|Verrouille une plage d'octets dans un fichier.|  
|[CFile::Open](../Topic/CFile::Open.md)|Ouvre sans risque un fichier avec une option d'erreur\-test.|  
|[CFile::Read](../Topic/CFile::Read.md)|Lit les données \(non tamponnées\) à partir d'un fichier à l'emplacement de fichier en cours.|  
|[CFile::Remove](../Topic/CFile::Remove.md)|Supprime le fichier spécifié \(fonction statique\).|  
|[CFile::Rename](../Topic/CFile::Rename.md)|Renomme le fichier spécifié \(fonction statique\).|  
|[CFile::Seek](../Topic/CFile::Seek.md)|Positionne le pointeur de fichier en cours.|  
|[CFile::SeekToBegin](../Topic/CFile::SeekToBegin.md)|Positionne le pointeur de fichier en cours au début du fichier.|  
|[CFile::SeekToEnd](../Topic/CFile::SeekToEnd.md)|Positionne le pointeur de fichier actuellement à la fin de le fichier.|  
|[CFile::SetFilePath](../Topic/CFile::SetFilePath.md)|Définit le chemin d'accès complet du fichier sélectionné.|  
|[CFile::SetLength](../Topic/CFile::SetLength.md)|Modifie la longueur du fichier.|  
|[CFile::SetStatus](../Topic/CFile::SetStatus.md)|Définit l'état du fichier spécifié \(statique, fonction virtuelle\).|  
|[CFile::UnlockRange](../Topic/CFile::UnlockRange.md)|Déverrouille une plage d'octets dans un fichier.|  
|[CFile::Write](../Topic/CFile::Write.md)|Écrit des données \(non tamponnées\) dans un fichier à l'emplacement de fichier en cours.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFile::operator HANDLE](../Topic/CFile::operator%20HANDLE.md)|Un handle vers un objet d' `CFile` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFile::hFileNull](../Topic/CFile::hFileNull.md)|Détermine si l'objet d' `CFile` a un handle valide.|  
|[CFile::m\_hFile](../Topic/CFile::m_hFile.md)|Contient généralement le handle de fichier du système d'exploitation.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CFile::m\_pTM](../Topic/CFile::m_pTM.md)|Pointeur vers l'objet d' `CAtlTransactionManager` .|  
  
## Notes  
 Il fournit directement des services non tamponnés et binaires d'entrée\/sortie du disque, et il prend en charge indirectement des fichiers texte et des fichiers de mémoire via ses classes dérivées.  `CFile` fonctionne conjointement avec la classe d' `CArchive` pour prendre en charge la sérialisation d'objets Microsoft Foundation Class\).  
  
 La relation hiérarchique entre cette classe et ses classes dérivées permet à votre programme pour traiter tous les fichiers objets via l'interface polymorphe d' `CFile` .  Un fichier de mémoire, par exemple, se comporte comme un fichier sur disque.  
  
 Utilisez `CFile` et ses classes dérivées pour l'E\/S de disque à caractère général.  Utilisez `ofstream` ou d'autres classes iostream Microsoft pour le texte mis en forme envoyé à un fichier sur disque.  
  
 Normalement, un fichier sur disque est ouvert automatiquement dans la construction d' `CFile` et fermé sur la destruction.  Les fonctions membres static vous permettent d'interroger le mode d'un fichier sans ouvrir le fichier.  
  
 Pour plus d'informations sur l'utilisation `CFile`, consultez les articles [fichiers dans MFC](../../mfc/files-in-mfc.md) et [gestion de fichiers](../../c-runtime-library/file-handling.md) dans *la référence de la bibliothèque Runtime*.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [DRAWCLI exemple MFC](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CStdioFile Class](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [Comment faire : utilisez la classe de fichier C ?](http://go.microsoft.com/fwlink/?LinkId=128046)