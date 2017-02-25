---
title: "CAtlFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlFile"
  - "ATL::CAtlFile"
  - "ATL.CAtlFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFile class"
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAtlFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit un wrapper mince autour de l'API de gestion de fichiers windows.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CAtlFile : public CHandle  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlFile::CAtlFile](../Topic/CAtlFile::CAtlFile.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlFile::Create](../Topic/CAtlFile::Create.md)|Appelez cette méthode pour créer ou ouvrir un fichier.|  
|[CAtlFile::Flush](../Topic/CAtlFile::Flush.md)|Appelez cette méthode pour effacer les mémoires tampons du fichier et pour provoquer toutes les données mises en mémoire tampon d'être écrit dans le fichier.|  
|[CAtlFile::GetOverlappedResult](../Topic/CAtlFile::GetOverlappedResult.md)|Appelez cette méthode pour obtenir les résultats d'une opération chevauchée sur le fichier.|  
|[CAtlFile::GetPosition](../Topic/CAtlFile::GetPosition.md)|Appelez cette méthode pour obtenir la position actuelle du pointeur de fichier du fichier.|  
|[CAtlFile::GetSize](../Topic/CAtlFile::GetSize.md)|Appelez cette méthode pour obtenir la taille en octets du fichier.|  
|[CAtlFile::LockRange](../Topic/CAtlFile::LockRange.md)|Appelez cette méthode pour verrouiller une zone dans le fichier pour empêcher d'autres processus d'y accéder.|  
|[CAtlFile::Read](../Topic/CAtlFile::Read.md)|Appelez cette méthode pour lire des données à partir d'un fichier démarrant à la position indiquée par le pointeur de fichier.|  
|[CAtlFile::Seek](../Topic/CAtlFile::Seek.md)|Appelez cette méthode pour déplacer le pointeur de fichier du fichier.|  
|[CAtlFile::SetSize](../Topic/CAtlFile::SetSize.md)|Appelez cette méthode pour définir la taille du fichier.|  
|[CAtlFile::UnlockRange](../Topic/CAtlFile::UnlockRange.md)|Appelez cette méthode pour déverrouiller une zone du fichier.|  
|[CAtlFile::Write](../Topic/CAtlFile::Write.md)|Appelez cette méthode pour écrire des données dans le fichier démarrant à la position indiquée par le pointeur de fichier.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlFile::m\_pTM](../Topic/CAtlFile::m_pTM.md)|Pointeur vers l'objet d' `CAtlTransactionManager`|  
  
## Notes  
 Utilisez cette classe lorsque les besoins de fichiers sont relativement simples, mais plus d'abstraction que l'API Windows fournit le est requis, sans inclure des dépendances MFC.  
  
## Hiérarchie d'héritage  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## Configuration requise  
 **Header:** atlfile.h  
  
## Voir aussi  
 [Exemple de bannière](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CHandle Class](../../atl/reference/chandle-class.md)