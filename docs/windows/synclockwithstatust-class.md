---
title: Synclockwithstatust, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs: C++
helpviewer_keywords: SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d1d2cd87c7a77501981904686f0bea0b3c7444e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT, classe
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `SyncTraits`  
 Un type qui peut prendre exclusif ou partagé possession d’une ressource.  
  
## <a name="remarks"></a>Notes  
 Représente un type qui peut prendre exclusif ou partagé possession d’une ressource.  
  
 La classe SyncLockWithStatusT est utilisée pour implémenter le [Mutex](../windows/mutex-class1.md) et [sémaphore](../windows/semaphore-class.md) classes.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT, constructeur](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialise une nouvelle instance de la classe SyncLockWithStatusT.|  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT, constructeur](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Initialise une nouvelle instance de la classe SyncLockWithStatusT.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[SyncLockWithStatusT::GetStatus, méthode](../windows/synclockwithstatust-getstatus-method.md)|Récupère l’état d’attente de l’objet SyncLockWithStatusT actuel.|  
|[SyncLockWithStatusT::IsLocked, méthode](../windows/synclockwithstatust-islocked-method.md)|Indique si l’objet SyncLockWithStatusT actuel possède une ressource ; l’objet SyncLockWithStatusT est *verrouillé*.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[SyncLockWithStatusT::status_, données de membre](../windows/synclockwithstatust-status-data-member.md)|Contient le résultat de l’objet sous-jacent attendre l’opération après une opération de verrouillage sur un objet basé sur l’objet SyncLockWithStatusT actuel.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Wrappers::Details, espace de noms](../windows/microsoft-wrl-wrappers-details-namespace.md)