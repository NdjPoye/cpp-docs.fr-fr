---
title: "IWorkerThreadClient Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IWorkerThreadClient"
  - "ATL::IWorkerThreadClient"
  - "IWorkerThreadClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IWorkerThreadClient interface"
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IWorkerThreadClient Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`IWorkerThreadClient` est l'interface implémentée par les clients de la classe de [CWorkerThread](../../atl/reference/cworkerthread-class.md) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
__interface IWorkerThreadClient  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CloseHandle](../Topic/IWorkerThreadClient::CloseHandle.md)|Appliquez cette méthode pour fermer le handle associé à cet objet.|  
|[Execute](../Topic/IWorkerThreadClient::Execute.md)|Appliquez cette méthode pour exécuter le code lorsque le handle associé à cet objet est signalé.|  
  
## Notes  
 Implémentez cette interface lorsque vous avez du code qui doit s'exécuter sur un thread de travail en réponse à un handle devenant signalé.  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)   
 [CWorkerThread Class](../../atl/reference/cworkerthread-class.md)