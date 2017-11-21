---
title: SRWLockExclusiveTraits (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs: C++
helpviewer_keywords: SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 75a232816e73cf19550ca897660708cdf200784f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits (structure)
Décrit des caractéristiques communes de la classe SRWLock en mode de verrou exclusif.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`Type`|Synonyme pour un pointeur vers le [SRWLOCK](../windows/srwlock-class.md) classe.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue, méthode](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Récupère un objet SRWLockExclusiveTraits qui est toujours non valide.|  
|[SRWLockExclusiveTraits::Unlock, méthode](../windows/srwlockexclusivetraits-unlock-method.md)|Libère le contrôle exclusif de l’objet SRWLock spécifié.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)