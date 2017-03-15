---
title: "Semaphore::Lock, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock (méthode)"
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Semaphore::Lock, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Attend jusqu'à ce que l’objet en cours, ou l’objet de sémaphore associé au handle spécifié, soit dans l’état signalé ou que l’intervalle de délai d’attente spécifié est écoulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `milliseconds`  
 L’intervalle de délai d’attente, en millisecondes. La valeur par défaut est INFINITE, qui attend indéfiniment.  
  
 `h`  
 Handle vers un objet de sémaphore.  
  
## <a name="return-value"></a>Valeur de retour  
 Un Details::SyncLockWithStatusT \< HandleTraits::SemaphoreTraits >  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
[Semaphore (classe)](../windows/semaphore-class.md)
 