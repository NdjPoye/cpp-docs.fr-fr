---
title: "Microsoft::WRL::Wrappers::HandleTraits, espace de noms | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleTraits (espace de noms)"
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Microsoft::WRL::Wrappers::HandleTraits, espace de noms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit les caractéristiques de types courants de ressources basé sur le handle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="structures"></a>Structures  
  
|Nom|Description|  
|----------|-----------------|  
|[CriticalSectionTraits (Structure)](../windows/criticalsectiontraits-structure.md)|Spécialisée un `CriticalSection` objet pour prendre en charge une section critique non valide ou une fonction d’annulation d’une section critique.|  
|[EventTraits (Structure)](../windows/eventtraits-structure.md)|Définit les caractéristiques d’un `Event` handle de classe.|  
|[FileHandleTraits (Structure)](../windows/filehandletraits-structure.md)|Définit les caractéristiques d’un descripteur de fichier.|  
|[HANDLENullTraits (Structure)](../windows/handlenulltraits-structure.md)|Définit les caractéristiques communes d’un handle non initialisé.|  
|[HANDLETraits (Structure)](../windows/handletraits-structure.md)|Définit les caractéristiques communes d’un handle.|  
|[MutexTraits (Structure)](../windows/mutextraits-structure.md)|Définit les caractéristiques communes à le [Mutex](../windows/mutex-class1.md) classe.|  
|[SemaphoreTraits (Structure)](../windows/semaphoretraits-structure.md)|Définit les caractéristiques communes d’un objet sémaphore.|  
|[SRWLockExclusiveTraits (Structure)](../windows/srwlockexclusivetraits-structure.md)|Décrit les caractéristiques communes de la `SRWLock` classe en mode de verrou exclusif.|  
|[SRWLockSharedTraits (Structure)](../windows/srwlocksharedtraits-structure.md)|Décrit les caractéristiques communes de la `SRWLock` classe en mode de verrou partagé.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::wrl::wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)