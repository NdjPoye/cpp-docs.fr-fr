---
title: "CAtlTransactionManager Class | Microsoft Docs"
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
  - "CAtlTransactionManager"
  - "atltransactionmanager/ATL::CAtlTransactionManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTransactionManager class"
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlTransactionManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de CAtlTransactionManager fournit un wrapper aux fonctions de \(KTM\) du gestionnaire de transactions de noyau.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
class CAtlTransactionManager;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlTransactionManager::~CAtlTransactionManager](../Topic/CAtlTransactionManager::~CAtlTransactionManager.md)|Destructeur de CAtlTransactionManager.|  
|[CAtlTransactionManager::CAtlTransactionManager](../Topic/CAtlTransactionManager::CAtlTransactionManager.md)|Constructeur de CAtlTransactionManager.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlTransactionManager::Close](../Topic/CAtlTransactionManager::Close.md)|Ferme un handle de transaction.|  
|[CAtlTransactionManager::Commit](../Topic/CAtlTransactionManager::Commit.md)|Les demandes ces la transaction validées.|  
|[CAtlTransactionManager::Create](../Topic/CAtlTransactionManager::Create.md)|Crée le handle de transaction.|  
|[CAtlTransactionManager::CreateFile](../Topic/CAtlTransactionManager::CreateFile.md)|Crée ou ouvre un fichier, un flux de fichiers, ou un répertoire comme opération traitée.|  
|[CAtlTransactionManager::DeleteFile](../Topic/CAtlTransactionManager::DeleteFile.md)|Supprime un fichier existant en tant qu'opération traitée.|  
|[CAtlTransactionManager::FindFirstFile](../Topic/CAtlTransactionManager::FindFirstFile.md)|Recherche un répertoire d'un fichier ou le sous\-répertoire en tant qu'opération traitée.|  
|[CAtlTransactionManager::GetFileAttributes](../Topic/CAtlTransactionManager::GetFileAttributes.md)|Récupère les attributs de système de fichiers pour un fichier spécifié ou un répertoire comme opération traitée.|  
|[CAtlTransactionManager::GetFileAttributesEx](../Topic/CAtlTransactionManager::GetFileAttributesEx.md)|Récupère les attributs de système de fichiers pour un fichier spécifié ou un répertoire comme opération traitée.|  
|[CAtlTransactionManager::GetHandle](../Topic/CAtlTransactionManager::GetHandle.md)|Retourne le handle de transaction.|  
|[CAtlTransactionManager::IsFallback](../Topic/CAtlTransactionManager::IsFallback.md)|Détermine si les appels de secours sont activés.|  
|[CAtlTransactionManager::MoveFile](../Topic/CAtlTransactionManager::MoveFile.md)|Déplace un fichier ou un dossier existant, y compris ses enfants, comme opération traitée.|  
|[CAtlTransactionManager::RegCreateKeyEx](../Topic/CAtlTransactionManager::RegCreateKeyEx.md)|Crée la clé de Registre spécifiée et l'associe à une transaction.  Si la clé existe déjà, la fonction l'ouvre.|  
|[CAtlTransactionManager::RegDeleteKey](../Topic/CAtlTransactionManager::RegDeleteKey.md)|Supprime une sous\-clé et ses valeurs de la vue spécifique à la plateforme spécifiée dans le Registre en tant qu'opération traitée.|  
|[CAtlTransactionManager::RegOpenKeyEx](../Topic/CAtlTransactionManager::RegOpenKeyEx.md)|Ouvre la clé de Registre spécifiée et l'associe à une transaction.|  
|[CAtlTransactionManager::Rollback](../Topic/CAtlTransactionManager::Rollback.md)|Demandes que la transaction est restaurée.|  
|[CAtlTransactionManager::SetFileAttributes](../Topic/CAtlTransactionManager::SetFileAttributes.md)|Définit les attributs d'un fichier ou un répertoire comme opération traitée.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlTransactionManager::m\_bFallback](../Topic/CAtlTransactionManager::m_bFallback.md)|`TRUE` si le secours est pris en charge ; `FALSE` sinon.|  
|[CAtlTransactionManager::m\_hTransaction](../Topic/CAtlTransactionManager::m_hTransaction.md)|Le handle de transaction.|  
  
## Notes  
  
## Hiérarchie d'héritage  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## Configuration requise  
 **Header:** atltransactionmanager.h  
  
## Voir aussi  
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)