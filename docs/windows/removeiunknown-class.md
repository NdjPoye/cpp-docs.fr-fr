---
title: Removeiunknown, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs: C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4434064e973626fa1274bf620aa6c8cd34dc99d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="removeiunknown-class"></a>RemoveIUnknown, classe
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Une classe.  
  
## <a name="remarks"></a>Notes  
 Crée un type qui est équivalent à une `IUnknown`-type de base, mais avec non virtuelle `QueryInterface`, `AddRef`, et `Release` fonctions membres.  
  
 Par défaut, les méthodes COM fournissent virtuel `QueryInterface`, `AddRef`et libérer des méthodes. Toutefois, `ComPtr` ne nécessite pas la surcharge de méthodes virtuelles. `RemoveIUnknown`élimine cette surcharge en fournissant privé et non virtuelle `QueryInterface`, `AddRef`, et `Release` méthodes.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`ReturnType`|Un synonyme pour un type qui est équivalent au paramètre de modèle `T` mais comporte des membres de IUnknown non virtuelles.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `T`  
  
 `RemoveIUnknown`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** client.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)