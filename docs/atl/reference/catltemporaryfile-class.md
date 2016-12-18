---
title: "CAtlTemporaryFile Class | Microsoft Docs"
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
  - "CAtlTemporaryFile"
  - "ATL.CAtlTemporaryFile"
  - "ATL::CAtlTemporaryFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTemporaryFile class"
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 18
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlTemporaryFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour la création et l'utilisation d'un fichier temporaire.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CAtlTemporaryFile  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md)|Constructeur.|  
|[CAtlTemporaryFile::~CAtlTemporaryFile](../Topic/CAtlTemporaryFile::~CAtlTemporaryFile.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlTemporaryFile::Close](../Topic/CAtlTemporaryFile::Close.md)|Appelez cette méthode pour fermer un fichier temporaire et pour supprimer son contenu ou les stocker sous le nom de fichier spécifié.|  
|[CAtlTemporaryFile::Create](../Topic/CAtlTemporaryFile::Create.md)|Appelez cette méthode pour créer un fichier temporaire.|  
|[CAtlTemporaryFile::Flush](../Topic/CAtlTemporaryFile::Flush.md)|Appelez cette méthode pour forcer les données restant dans la mémoire tampon de fichier pour écrire dans le fichier temporaire.|  
|[CAtlTemporaryFile::GetPosition](../Topic/CAtlTemporaryFile::GetPosition.md)|Appelez cette méthode pour obtenir la position actuelle du pointeur de fichier.|  
|[CAtlTemporaryFile::GetSize](../Topic/CAtlTemporaryFile::GetSize.md)|Appelez cette méthode pour obtenir la taille en octets du fichier temporaire.|  
|[CAtlTemporaryFile::HandsOff](../Topic/CAtlTemporaryFile::HandsOff.md)|Appelez cette méthode pour dissocier le fichier de l'objet d' `CAtlTemporaryFile` .|  
|[CAtlTemporaryFile::HandsOn](../Topic/CAtlTemporaryFile::HandsOn.md)|Appelez cette méthode pour ouvrir un fichier temporaire existant et pour positionner le pointeur à la fin de le fichier.|  
|[CAtlTemporaryFile::LockRange](../Topic/CAtlTemporaryFile::LockRange.md)|Appelez cette méthode pour verrouiller une zone dans le fichier pour empêcher d'autres processus d'y accéder.|  
|[CAtlTemporaryFile::Read](../Topic/CAtlTemporaryFile::Read.md)|Appelez cette méthode pour lire les données du fichier temporaire de départ à la position indiquée par le pointeur de fichier.|  
|[CAtlTemporaryFile::Seek](../Topic/CAtlTemporaryFile::Seek.md)|Appelez cette méthode pour déplacer le pointeur de fichier du fichier temporaire.|  
|[CAtlTemporaryFile::SetSize](../Topic/CAtlTemporaryFile::SetSize.md)|Appelez cette méthode pour définir la taille du fichier temporaire.|  
|[CAtlTemporaryFile::TempFileName](../Topic/CAtlTemporaryFile::TempFileName.md)|Appelez cette méthode pour retourner le nom de fichier temporaire.|  
|[CAtlTemporaryFile::UnlockRange](../Topic/CAtlTemporaryFile::UnlockRange.md)|Appelez cette méthode pour déverrouiller une zone du fichier temporaire.|  
|[CAtlTemporaryFile::Write](../Topic/CAtlTemporaryFile::Write.md)|Appelez cette méthode pour écrire des données dans le fichier temporaire de départ à la position indiquée par le pointeur de fichier.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlTemporaryFile::operator HANDLE](../Topic/CAtlTemporaryFile::operator%20HANDLE.md)|Retourne un handle au fichier temporaire.|  
  
## Notes  
 `CAtlTemporaryFile` facilite la création et l'utilisation d'un fichier temporaire.  Le fichier est nommé automatiquement, ouvrez, fermé, et supprimé.  Si le contenu du fichier est requis après que le fichier soit fermé, ils peuvent être enregistrés dans un nouveau fichier portant un nom spécifié.  
  
## Configuration requise  
 **Header:** atlfile.h  
  
## Exemple  
 Consultez l'exemple pour [CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md).  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CAtlFile Class](../../atl/reference/catlfile-class.md)