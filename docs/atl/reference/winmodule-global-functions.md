---
title: Fonctions globales WinModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c477f4500bd4fe78f21f04c58b02d1b493f72c01
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="winmodule-global-functions"></a>Fonctions globales WinModule
Ces fonctions fournissent la prise en charge de `_AtlCreateWndData` structure d’opérations.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Cette fonction est utilisée pour initialiser et ajouter une structure `_AtlCreateWndData`.|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Appelez cette fonction pour extraire une structure `_AtlCreateWndData` existante.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  `            
##  <a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData  
 Cette fonction est utilisée pour initialiser et ajouter une structure `_AtlCreateWndData`.  
   
```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWinModule`  
 Pointeur vers un module [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) structure.  
  
 `pData`  
 Pointeur vers le [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) structure à être initialisés et ajoutés au module actuel.  
  
 `pObject`  
 Pointeur vers un objet **cela** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Initialise une `_AtlCreateWndData` structure, qui est utilisé pour stocker le **cela** pointeur utilisé pour faire référence à des instances de classe et l’ajoute à la liste référencée par un module `_ATL_WIN_MODULE70` structure. Appelé par [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).  
  
##  <a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData  
 Appelez cette fonction pour extraire une structure `_AtlCreateWndData` existante.  
 
```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWinModule`  
 Pointeur vers un module [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) structure.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction extrait existant `_AtlCreateWndData` structure à partir de la liste référencée par un module `_ATL_WIN_MODULE70` structure.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)

