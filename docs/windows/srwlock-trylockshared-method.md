---
title: "SRWLOCK::trylockshared, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs: C++
helpviewer_keywords: TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 375e4f583531ad1e4eb16b29307445f04d982aea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared, méthode
Tente d’acquérir un objet SRWLock en mode partagé pour l’objet SRWLock actuelle ou spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lock`  
 Pointeur vers un objet SRWLock.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, un objet SRWLock en mode partagé et le thread appelant prend possession du verrou. Sinon, une SRWLock de l’objet dont l’état n’est pas valide.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [SRWLock, classe](../windows/srwlock-class.md)