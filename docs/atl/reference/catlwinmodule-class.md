---
title: "CAtlWinModule Class | Microsoft Docs"
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
  - "ATL::CAtlWinModule"
  - "ATL.CAtlWinModule"
  - "CAtlWinModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlWinModule class"
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlWinModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit la prise en charge des composants de fenêtrage ATL.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CAtlWinModule : public _ATL_WIN_MODULE  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlWinModule::CAtlWinModule](../Topic/CAtlWinModule::CAtlWinModule.md)|Constructeur.|  
|[CAtlWinModule::~CAtlWinModule](../Topic/CAtlWinModule::~CAtlWinModule.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlWinModule::AddCreateWndData](../Topic/CAtlWinModule::AddCreateWndData.md)|Ajoute un objet de données.|  
|[CAtlWinModule::ExtractCreateWndData](../Topic/CAtlWinModule::ExtractCreateWndData.md)|Retourne un pointeur vers l'objet de données du module de fenêtre.|  
  
## Notes  
 Cette classe fournit la prise en charge de toutes les classes ATL qui nécessitent des fonctionnalités de fenêtrage.  
  
## Hiérarchie d'héritage  
 [\_ATL\_WIN\_MODULE](../Topic/_ATL_WIN_MODULE.md)  
  
 `CAtlWinModule`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [\_ATL\_WIN\_MODULE](../Topic/_ATL_WIN_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Module, classes](../../atl/atl-module-classes.md)