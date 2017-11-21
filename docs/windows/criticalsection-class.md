---
title: CriticalSection, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs: C++
helpviewer_keywords: CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89587f87bd71d2688bba2c128d28c01212b50b71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsection-class"></a>CriticalSection (classe)
Représente un objet de section critique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CriticalSection;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="constructor"></a>Constructeur  
  
|Nom|Description|  
|----------|-----------------|  
|[CriticalSection::CriticalSection, constructeur](../windows/criticalsection-criticalsection-constructor.md)|Initialise un objet de synchronisation qui est similaire à un objet mutex, mais peut être utilisé par uniquement les threads d’un processus unique.|  
|[CriticalSection::~CriticalSection, destructeur](../windows/criticalsection-tilde-criticalsection-destructor.md)|Désinitialise et détruit l’objet CriticalSection actuel.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CriticalSection::TryLock, méthode](../windows/criticalsection-trylock-method.md)|Tente d’entrer une section critique sans se bloquer. Si l’appel réussit, le thread appelant prend la propriété de la section critique.|  
|[CriticalSection::Lock, méthode](../windows/criticalsection-lock-method.md)|Attend que la propriété de l’objet spécifié de section critique. La fonction retourne quand le thread appelant est accordé à la propriété.|  
|[CriticalSection::IsValid, méthode](../windows/criticalsection-isvalid-method.md)|Indique si la section critique en cours est valide.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CriticalSection::cs_, données de membre](../windows/criticalsection-cs-data-member.md)|Déclare un membre de données de section critique.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `CriticalSection`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)