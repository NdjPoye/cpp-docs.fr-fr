---
title: "Classe d’événements (Windows Runtime C++ modèle bibliothèque) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs: C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4647a8b1001cd6acd6b70a3d15f127c8e3891c1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="event-class-windows-runtime-c-template-library"></a>Event, classe (bibliothèque de modèles Windows Runtime C++)
Représente un événement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Event::Event, constructeur (bibliothèque de modèles Windows Runtime C++)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Initialise une nouvelle instance de la classe Event.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Event::operator=, opérateur](../windows/event-operator-assign-operator.md)|Assigne la référence Event spécifiée à l'instance Event actuelle.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)