---
title: "Microsoft::WRL::Wrappers, espace de noms | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Wrappers (espace de noms)"
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Microsoft::WRL::Wrappers, espace de noms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les types de wrapper Resource Acquisition est l’initialisation (RAII) qui simplifient la gestion de la durée de vie des objets, les chaînes et les handles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace Microsoft::WRL::Wrappers;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="typedefs"></a>Typedef  
  
|Nom|Description|  
|----------|-----------------|  
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|  
  
### <a name="classes"></a>Classes  
  
|Nom|Description|  
|----------|-----------------|  
|[CriticalSection (classe)](../windows/criticalsection-class.md)|Représente un objet de section critique.|  
|[Classe d’événements (Windows Runtime C++ STL)](../windows/event-class-windows-runtime-cpp-template-library.md)|Représente un événement.|  
|[HandleT (classe)](../windows/handlet-class.md)|Représente un handle d’un objet.|  
|[Hstring, classe](../windows/hstring-class.md)|Prend en charge HSTRING poignées de manipulation.|  
|[Hstringreference, classe](../windows/hstringreference-class.md)|Représente une chaîne HSTRING créé à partir d’une chaîne existante.|  
|[Mutex (classe)](../windows/mutex-class1.md)|Représente un objet de synchronisation qui contrôle exclusivement une ressource partagée.|  
|[Roinitializewrapper, classe](../windows/roinitializewrapper-class.md)|Initialise la [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[Semaphore (classe)](../windows/semaphore-class.md)|Représente un objet de synchronisation qui contrôle une ressource partagée prenant en charge un nombre limité d’utilisateurs.|  
|[SRWLock (classe)](../windows/srwlock-class.md)|Représente un verrou SRW.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)