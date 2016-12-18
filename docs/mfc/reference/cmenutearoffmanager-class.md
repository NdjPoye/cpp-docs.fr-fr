---
title: "CMenuTearOffManager Class | Microsoft Docs"
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
  - "CMenuTearOffManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenuTearOffManager class"
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMenuTearOffManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère des menus volants.  Un menu volant est un menu dans la barre de menus.  L'utilisateur peut supprimer un menu volant de la barre de menus, rendre flottant le menu volant.  
  
## Syntaxe  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](../Topic/CMenuTearOffManager::CMenuTearOffManager.md)|Construit un objet `CMenuTearOffManager`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMenuTearOffManager::Build](../Topic/CMenuTearOffManager::Build.md)||  
|[CMenuTearOffManager::GetRegPath](../Topic/CMenuTearOffManager::GetRegPath.md)||  
|[CMenuTearOffManager::Initialize](../Topic/CMenuTearOffManager::Initialize.md)|Initialise un objet `CMenuTearOffManager`.|  
|[CMenuTearOffManager::IsDynamicID](../Topic/CMenuTearOffManager::IsDynamicID.md)||  
|[CMenuTearOffManager::Parse](../Topic/CMenuTearOffManager::Parse.md)||  
|[CMenuTearOffManager::Reset](../Topic/CMenuTearOffManager::Reset.md)||  
|[CMenuTearOffManager::SetInUse](../Topic/CMenuTearOffManager::SetInUse.md)||  
|[CMenuTearOffManager::SetupTearOffMenus](../Topic/CMenuTearOffManager::SetupTearOffMenus.md)||  
  
## Notes  
 Pour utiliser des menus volants dans votre application, vous devez disposer d'un objet d' `CMenuTearOffManager` .  Dans la plupart des cas, vous ne créez pas ou n'initialiserez pas l'objet d' `CMenuTearOffManager` directement.  Cela est contrôlé pour lorsque vous appelez la fonction de [CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md) .  
  
## Exemple  
 L'exemple suivant montre comment construire et initialiser un objet d' `CMenuTearOffManager` en appelant la méthode d' `CWinAppEX::EnableTearOffMenus` .  Cet extrait de code fait partie d' [Exemple de protection de Word](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/CPP/cmenutearoffmanager-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxmenutearoffmanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)