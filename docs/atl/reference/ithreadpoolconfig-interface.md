---
title: "IThreadPoolConfig Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IThreadPoolConfig"
  - "ATL::IThreadPoolConfig"
  - "ATL.IThreadPoolConfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadPoolConfig interface"
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# IThreadPoolConfig Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette interface fournit des méthodes pour configurer un pool de threads.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      __interface  
__declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660"))  
IThreadPoolConfig :  
public IUnknown  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[GetSize](../Topic/IThreadPoolConfig::GetSize.md)|Appelez cette méthode pour obtenir le nombre de threads dans le pool.|  
|[GetTimeout](../Topic/IThreadPoolConfig::GetTimeout.md)|Appelez cette méthode pour obtenir le temps maximum en millisecondes que le pool de threads attend un thread s'arrête.|  
|[SetSize](../Topic/IThreadPoolConfig::SetSize.md)|Appelez cette méthode pour définir le nombre de threads dans le pool.|  
|[SetTimeout](../Topic/IThreadPoolConfig::SetTimeout.md)|Appelez cette méthode pour définir le temps maximum en millisecondes que le pool de threads attend un thread s'arrête.|  
  
## Notes  
 Cette interface est implémentée par [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)   
 [CThreadPool Class](../../atl/reference/cthreadpool-class.md)