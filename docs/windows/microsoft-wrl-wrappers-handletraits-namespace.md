---
title: Microsoft::wrl::wrappers::HandleTraits Namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs: C++
helpviewer_keywords: HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aec9ff1b4294257f692d76a96960820379116b0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits, espace de noms
Décrit les caractéristiques de types courants de ressources basé sur le handle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="structures"></a>Structures  
  
|Nom|Description|  
|----------|-----------------|  
|[CriticalSectionTraits, structure](../windows/criticalsectiontraits-structure.md)|Spécialise une `CriticalSection` objet pour prendre en charge une section critique non valide ou une fonction d’annulation d’une section critique.|  
|[EventTraits, structure](../windows/eventtraits-structure.md)|Définit les caractéristiques d’un `Event` handle de classe.|  
|[FileHandleTraits, structure](../windows/filehandletraits-structure.md)|Définit les caractéristiques d’un handle de fichier.|  
|[HANDLENullTraits, structure](../windows/handlenulltraits-structure.md)|Définit les caractéristiques communes d’un handle non initialisé.|  
|[HANDLETraits, structure](../windows/handletraits-structure.md)|Définit les caractéristiques communes d’un handle.|  
|[MutexTraits, structure](../windows/mutextraits-structure.md)|Définit les caractéristiques communes de la [Mutex](../windows/mutex-class1.md) classe.|  
|[SemaphoreTraits, structure](../windows/semaphoretraits-structure.md)|Définit les caractéristiques communes d’un objet sémaphore.|  
|[SRWLockExclusiveTraits, structure](../windows/srwlockexclusivetraits-structure.md)|Décrit des caractéristiques communes de la `SRWLock` classe en mode de verrou exclusif.|  
|[SRWLockSharedTraits, structure](../windows/srwlocksharedtraits-structure.md)|Décrit des caractéristiques communes de la `SRWLock` classe en mode de verrou partagé.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)