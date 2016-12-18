---
title: "CAtlFileMappingBase Class | Microsoft Docs"
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
  - "ATL.CAtlFileMappingBase"
  - "ATL::CAtlFileMappingBase"
  - "CAtlFileMappingBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMappingBase class"
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlFileMappingBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un fichier mappé en mémoire.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CAtlFileMappingBase  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](../Topic/CAtlFileMappingBase::CAtlFileMappingBase.md)|Constructeur.|  
|[CAtlFileMappingBase::~CAtlFileMappingBase](../Topic/CAtlFileMappingBase::~CAtlFileMappingBase.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](../Topic/CAtlFileMappingBase::CopyFrom.md)|Appelez cette méthode pour copier d'un objet de mappage de fichier.|  
|[CAtlFileMappingBase::GetData](../Topic/CAtlFileMappingBase::GetData.md)|Appelez cette méthode pour obtenir les données d'un objet de mappage de fichier.|  
|[CAtlFileMappingBase::GetHandle](../Topic/CAtlFileMappingBase::GetHandle.md)|Appelez cette méthode pour retourner le handle de fichier.|  
|[CAtlFileMappingBase::GetMappingSize](../Topic/CAtlFileMappingBase::GetMappingSize.md)|Appelez cette méthode pour obtenir la taille de mappage d'un objet de mappage de fichier.|  
|[CAtlFileMappingBase::MapFile](../Topic/CAtlFileMappingBase::MapFile.md)|Appelez cette méthode pour créer un objet de mappage de fichier.|  
|[CAtlFileMappingBase::MapSharedMem](../Topic/CAtlFileMappingBase::MapSharedMem.md)|Appelez cette méthode pour créer un objet de mappage de fichier qui permet l'accès complet à tous les processus.|  
|[CAtlFileMappingBase::OpenMapping](../Topic/CAtlFileMappingBase::OpenMapping.md)|Appelez cette méthode pour retourner un handle vers l'objet de mappage de fichier.|  
|[CAtlFileMappingBase::Unmap](../Topic/CAtlFileMappingBase::Unmap.md)|Appelez cette méthode pour annuler le mappage d'un objet de mappage de fichier.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlFileMappingBase::operator \=](../Topic/CAtlFileMappingBase::operator%20=.md)|Définit l'objet de mappage de fichier en cours vers un autre objet de mappage de fichier.|  
  
## Notes  
 Le mappage du fichier est l'association du contenu d'un fichier avec une partie de l'espace d'adressage virtuel d'un processus.  Cette classe fournit des méthodes pour créer des objets de mappage de fichier que la règle d'autorisation programme facilement pour accéder et partager des données.  
  
 Pour plus d'informations, consultez [mappage du fichier](http://msdn.microsoft.com/library/windows/desktop/aa366556) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlfile.h  
  
## Voir aussi  
 [CAtlFileMapping Class](../../atl/reference/catlfilemapping-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)