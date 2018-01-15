---
title: MixIn (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::MixIn
dev_langs: C++
helpviewer_keywords: MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 883e952dde579cce3f5a65ba4a453f98ddbb4740
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mixin-structure"></a>MixIn (structure)
Garantit qu'une classe d'exécution dérive des interfaces du Windows Runtime, le cas échéant, puis des interfaces du COM classique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Derived`  
 Un type dérivé de la [implémente](../windows/implements-structure.md) structure.  
  
 `MixInType`  
 Type de base.  
  
 `hasImplements`  
 `true`Si `MixInType` est dérivé de l’implémentation actuelle du type de base ; `false` dans le cas contraire.  
  
## <a name="remarks"></a>Notes  
 Si une classe est dérivée de Windows Runtime et les interfaces de classe COM, la liste de déclaration de classe doit répertorier tout d’abord toutes les interfaces Windows Runtime et puis des interfaces tout COM classique. MixIn garantit que les interfaces sont spécifiées dans l’ordre correct.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `MixIn`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)