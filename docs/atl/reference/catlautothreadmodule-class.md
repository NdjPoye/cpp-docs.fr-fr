---
title: Classe de CAtlAutoThreadModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlAutoThreadModule
- CAtlAutoThreadModule
- ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 09f4a7061ce1e4a09d0d27bd90dfcc16a37f4d5b
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodule-class"></a>Classe de CAtlAutoThreadModule
Cette classe implémente un pool de threads cloisonnés COM serveur.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>Remarques  
 `CAtlAutoThreadModule`dérive de [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) et implémente un pool de threads cloisonnés COM serveur. `CAtlAutoThreadModule`utilise [CComApartment](../../atl/reference/ccomapartment-class.md) pour gérer un cloisonnement pour chaque thread dans le module.  
  
 Vous devez utiliser le [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) macro dans votre définition de l’objet classe pour spécifier [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) en tant que la fabrique de classe. Vous devez ensuite ajouter une instance unique d’une classe dérivée de `CAtlAutoThreadModuleT` comme `CAtlAutoThreadModule`. Exemple :  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Cette classe remplace obsolète [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) classe.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [CAtlAutoThreadModuleT (classe)](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule (classe)](../../atl/reference/iatlautothreadmodule-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)
