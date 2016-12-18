---
title: "CShellManager Class | Microsoft Docs"
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
  - "CShellManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CShellManager class"
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CShellManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente plusieurs méthodes qui vous permettent d'utiliser des pointeurs vers les listes d'identificateur \(PIDLs\).  
  
## Syntaxe  
  
```  
class CShellManager : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CShellManager::CShellManager](../Topic/CShellManager::CShellManager.md)|Construit un objet `CShellManager`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CShellManager::BrowseForFolder](../Topic/CShellManager::BrowseForFolder.md)|Affiche une boîte de dialogue qui permet à l'utilisateur de sélectionner un dossier de shell.|  
|[CShellManager::ConcatenateItem](../Topic/CShellManager::ConcatenateItem.md)|Concatène deux PIDLs.|  
|[CShellManager::CopyItem](../Topic/CShellManager::CopyItem.md)|Crée un nouveau PIDL et copie le PIDL fourni à celui\-ci.|  
|[CShellManager::CreateItem](../Topic/CShellManager::CreateItem.md)|Crée un nouveau PIDL de la taille spécifiée.|  
|[CShellManager::FreeItem](../Topic/CShellManager::FreeItem.md)|Supprime le PIDL fourni.|  
|[CShellManager::GetItemCount](../Topic/CShellManager::GetItemCount.md)|Retourne le nombre d'éléments dans le PIDL fourni.|  
|[CShellManager::GetItemSize](../Topic/CShellManager::GetItemSize.md)|Retourne la taille du PIDL fourni.|  
|[CShellManager::GetNextItem](../Topic/CShellManager::GetNextItem.md)|Retourne l'élément suivant du PIDL.|  
|[CShellManager::GetParentItem](../Topic/CShellManager::GetParentItem.md)|Récupère l'élément parent de l'élément fourni.|  
|[CShellManager::ItemFromPath](../Topic/CShellManager::ItemFromPath.md)|Récupère le PIDL pour l'élément identifié par le chemin d'accès fourni.|  
  
## Notes  
 Les méthodes d' `CShellManager` fichier toute le cas avec PIDLs.  Un PIDL est un identificateur unique d'un objet de shell.  
  
 Vous ne devez pas créer un objet d' `CShellManager` manuellement.  Il sera créé automatiquement par l'infrastructure de votre application.  Toutefois, vous devez appeler [CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md) pendant le processus d'initialisation de votre application.  Pour obtenir un pointeur vers le gestionnaire de shell pour votre application, appelez [CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxshellmanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)