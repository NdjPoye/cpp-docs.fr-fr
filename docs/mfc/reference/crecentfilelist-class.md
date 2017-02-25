---
title: "CRecentFileList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRecentFileList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecentFileList class"
  - "fichiers (C++), most recently used"
  - "fichiers MRU"
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CRecentFileList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contrôle prend en charge de la liste des derniers fichiers utilisés de \(MRU\).  
  
## Syntaxe  
  
```  
class CRecentFileList  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecentFileList::CRecentFileList](../Topic/CRecentFileList::CRecentFileList.md)|Construit un objet `CRecentFileList`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecentFileList::Add](../Topic/CRecentFileList::Add.md)|Ajoute un fichier à la liste des fichiers récents.|  
|[CRecentFileList::GetDisplayName](../Topic/CRecentFileList::GetDisplayName.md)|Fournit un nom complet de l'affichage d'un nom de fichier MRU.|  
|[CRecentFileList::GetSize](../Topic/CRecentFileList::GetSize.md)|Récupère le nombre de fichiers dans la liste des fichiers récents.|  
|[CRecentFileList::ReadList](../Topic/CRecentFileList::ReadList.md)|Lit la liste des fichiers récents du Registre ou le fichier .ini.|  
|[CRecentFileList::Remove](../Topic/CRecentFileList::Remove.md)|Supprime un fichier de la liste des fichiers récents.|  
|[CRecentFileList::UpdateMenu](../Topic/CRecentFileList::UpdateMenu.md)|Met à jour l'affichage de menu de la liste des fichiers récents.|  
|[CRecentFileList::WriteList](../Topic/CRecentFileList::WriteList.md)|Écrit la liste des fichiers récents du Registre ou le fichier .ini.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecentFileList::operator](../Topic/CRecentFileList::operator.md)|Retourne un objet d' `CString` à une position donnée.|  
  
## Notes  
 Les fichiers peuvent être ajoutés ou supprimés de la liste des fichiers récents, la liste des fichiers peut être lue dans ou écrite dans le Registre ou un fichier .ini, et le menu affiche la liste des fichiers récents peut être mis à jour.  
  
 Pour plus d'informations sur les éléments de menu MRU, consultez  
  
-   Article de la Base de connaissances Q243751 : HOWTO : Ajoutez les gestionnaires de commandes pour les éléments de menu MRU dans l'application MFC  
  
## Hiérarchie d'héritage  
 `CRecentFileList`  
  
## Configuration requise  
 **Header:** afxadv.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)