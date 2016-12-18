---
title: "CNoWorkerThread Class | Microsoft Docs"
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
  - "ATL::CNoWorkerThread"
  - "ATL.CNoWorkerThread"
  - "CNoWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoWorkerThread class"
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CNoWorkerThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cette classe comme argument pour le paramètre de modèle d' `MonitorClass` mette en cache des classes si vous souhaitez désactiver la maintenance dynamique de cache.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CNoWorkerThread  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CNoWorkerThread::AddHandle](../Topic/CNoWorkerThread::AddHandle.md)|Équivalent non fonctionnel de [CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md).|  
|[CNoWorkerThread::AddTimer](../Topic/CNoWorkerThread::AddTimer.md)|Équivalent non fonctionnel de [CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md).|  
|[CNoWorkerThread::GetThreadHandle](../Topic/CNoWorkerThread::GetThreadHandle.md)|Équivalent non fonctionnel de [CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md).|  
|[CNoWorkerThread::GetThreadId](../Topic/CNoWorkerThread::GetThreadId.md)|Équivalent non fonctionnel de [CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md).|  
|[CNoWorkerThread::Initialize](../Topic/CNoWorkerThread::Initialize.md)|Équivalent non fonctionnel de [CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md).|  
|[CNoWorkerThread::RemoveHandle](../Topic/CNoWorkerThread::RemoveHandle.md)|Équivalent non fonctionnel de [CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md).|  
|[CNoWorkerThread::Shutdown](../Topic/CNoWorkerThread::Shutdown.md)|Équivalent non fonctionnel de [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md).|  
  
## Notes  
 Cette classe fournit la même interface publique que [CWorkerThread](../../atl/reference/cworkerthread-class.md).  Supposée cette interface est fournie par le paramètre de modèle d' `MonitorClass` aux classes de cache.  
  
 Les méthodes de cette classe sont implémentées pour ne rien.  Les méthodes qui retournent un retour S\_OK HRESULT toujours, et les méthodes qui retournent un retour 0 de HANDLE ou d'ID de thread.  
  
## Configuration requise  
 **Header:** atlutil.h