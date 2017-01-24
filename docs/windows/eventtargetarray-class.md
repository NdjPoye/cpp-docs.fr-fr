---
title: "EventTargetArray, classe | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray (classe)"
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l’infrastructure/FAO et n’est pas destinée à être utilisée directement à partir de votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Notes  
 Représente un tableau des gestionnaires d’événements.  
  
 Les gestionnaires d’événements qui sont associés un [EventSource](../windows/eventsource-class.md) objet sont stockées dans un membre de données EventTargetArray.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Eventtargetarray::eventtargetarray, constructeur](../windows/eventtargetarray-eventtargetarray-constructor.md)|Initialise une nouvelle instance de la classe EventTargetArray.|  
|[EventTargetArray :: ~ EventTargetArray, destructeur](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Deinitializes de la classe EventTargetArray en cours.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Eventtargetarray::AddTail, méthode](../windows/eventtargetarray-addtail-method.md)|Ajoute le Gestionnaire d’événements spécifié à la fin du tableau interne de gestionnaires d’événements.|  
|[Eventtargetarray::BEGIN, méthode](../windows/eventtargetarray-begin-method.md)|Obtient l’adresse du premier élément du tableau interne de gestionnaires d’événements.|  
|[Eventtargetarray::end, méthode](../windows/eventtargetarray-end-method.md)|Obtient l’adresse du dernier élément dans un tableau interne de gestionnaires d’événements.|  
|[Eventtargetarray::Length, méthode](../windows/eventtargetarray-length-method.md)|Obtient le nombre actuel d’éléments dans un tableau interne de gestionnaires d’événements.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `EventTargetArray`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::wrl::Details Namespace](../windows/microsoft-wrl-details-namespace.md)