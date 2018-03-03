---
title: Microsoft::wrl::wrappers Namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
dev_langs:
- C++
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f7633bcd784fa7b9b5f7255e25e8ddc52c5b93db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers, espace de noms
Définit les types de wrapper de l’initialisation d’est d’Acquisition de ressources (RAII) qui simplifient la gestion de la durée de vie des objets, les chaînes et les handles.  
  
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
|[CriticalSection, classe](../windows/criticalsection-class.md)|Représente un objet de section critique.|  
|[Event, classe (bibliothèque de modèles Windows Runtime C++)](../windows/event-class-windows-runtime-cpp-template-library.md)|Représente un événement.|  
|[HandleT, classe](../windows/handlet-class.md)|Représente un handle d’un objet.|  
|[HString, classe](../windows/hstring-class.md)|Prend en charge pour la manipulation des descripteurs de HSTRING.|  
|[HStringReference, classe](../windows/hstringreference-class.md)|Représente un HSTRING est créé à partir d’une chaîne existante.|  
|[Mutex (classe)](../windows/mutex-class1.md)|Représente un objet de synchronisation qui contrôle exclusivement une ressource partagée.|  
|[RoInitializeWrapper, classe](../windows/roinitializewrapper-class.md)|Initialise le Windows Runtime.|  
|[Semaphore, classe](../windows/semaphore-class.md)|Représente un objet de synchronisation qui contrôle une ressource partagée prenant en charge un nombre limité d’utilisateurs.|  
|[SRWLock, classe](../windows/srwlock-class.md)|Représente un verrou de lecteur/writer compacte.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)