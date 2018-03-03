---
title: Eventtargetarray::eventtargetarray, constructeur | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e8c8ada61a18437ed159452355e8286bc9d190f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray, constructeur
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hr`  
 Après les opérations de ce constructeur, paramètre `hr` indique si l’allocation du tableau a réussi ou échoué. Le tableau suivant répertorie les valeurs possibles pour `hr`.  
  
 S_OK  
 L’opération a réussi.  
  
 E_OUTOFMEMORY  
 Impossible d’allouer la mémoire pour le tableau.  
  
 S_FALSE  
 Paramètre `items` est inférieur ou égal à zéro.  
  
 `items`  
 Le nombre d’éléments de tableau à allouer.  
  
## <a name="remarks"></a>Notes  
 Initialise une nouvelle instance de la classe EventTargetArray.  
  
 EventTargetArray est utilisé pour conserver un tableau de gestionnaires d’événements dans un objet source d’événement.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** event.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [EventTargetArray (classe)](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)