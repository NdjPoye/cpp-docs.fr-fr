---
title: Eventtargetarray, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::EventTargetArray
dev_langs: C++
helpviewer_keywords: EventTargetArray class
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac591a1d27792d3b825336ed46e38fa5d002fa73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="eventtargetarray-class"></a>EventTargetArray, classe
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Notes  
 Représente un tableau de gestionnaires d’événements.  
  
 Les gestionnaires d’événements qui sont associés un [EventSource](../windows/eventsource-class.md) objet sont stockées dans un membre de données EventTargetArray protégé.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[EventTargetArray::EventTargetArray, constructeur](../windows/eventtargetarray-eventtargetarray-constructor.md)|Initialise une nouvelle instance de la classe EventTargetArray.|  
|[EventTargetArray::~EventTargetArray, destructeur](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Désinitialise l’EventTargetArray (classe) en cours.|  
  
### <a name="public-methods"></a>Méthodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[EventTargetArray::AddTail, méthode](../windows/eventtargetarray-addtail-method.md)|Ajoute le Gestionnaire d’événements spécifié à la fin du tableau interne de gestionnaires d’événements.|  
|[EventTargetArray::Begin, méthode](../windows/eventtargetarray-begin-method.md)|Obtient l’adresse du premier élément dans le tableau interne de gestionnaires d’événements.|  
|[EventTargetArray::End, méthode](../windows/eventtargetarray-end-method.md)|Obtient l’adresse du dernier élément dans le tableau interne de gestionnaires d’événements.|  
|[EventTargetArray::Length, méthode](../windows/eventtargetarray-length-method.md)|Obtient le nombre actuel d’éléments dans le tableau interne de gestionnaires d’événements.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `EventTargetArray`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)