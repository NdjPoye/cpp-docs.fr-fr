---
title: Classe de CAtlWinModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
caps.latest.revision: 20
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
ms.openlocfilehash: 6db3ae9e610605524683e984f2aba602b1daf0d4
ms.lasthandoff: 02/24/2017

---
# <a name="catlwinmodule-class"></a>CAtlWinModule (classe)
Cette classe prend en charge pour les composants de fenêtrage ATL.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|Constructeur.|  
|[CAtlWinModule :: ~ CAtlWinModule](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Ajoute un objet de données.|  
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Retourne un pointeur vers l’objet de données de fenêtre module.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe prend en charge toutes les classes ATL qui ont besoin de fonctionnalités de fenêtrage.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)  
  
 `CAtlWinModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData  
 Cette méthode initialise et ajoute une `_AtlCreateWndData` structure.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pData`  
 Pointeur vers le `_AtlCreateWndData` structure à être initialisés et ajoutés au module actuel.  
  
 `pObject`  
 Pointeur vers un objet **cela** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode appelle [AtlWinModuleAddCreateWndData](http://msdn.microsoft.com/library/8463a6ed-07ea-4aad-92ec-ded681601b32) qui initialise un [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) structure. Cette structure stockera la **cela** pointeur, utilisé pour obtenir l’instance de classe dans les procédures de fenêtre.  
  
##  <a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule  
 Constructeur.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>Remarques  
 Si l’initialisation échoue, un **EXCEPTION_NONCONTINUABLE** exception est levée.  
  
##  <a name="dtor"></a>CAtlWinModule :: ~ CAtlWinModule  
 Destructeur.  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les ressources attribuées.  
  
##  <a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData  
 Cette méthode retourne un pointeur vers un `_AtlCreateWndData` structure.  
  
```
void* ExtractCreateWndData();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le `_AtlCreateWndData` structure ajouté précédemment avec [CAtlWinModule::AddCreateWndData](#addcreatewnddata), ou NULL si aucun objet n’est disponible.  
  
## <a name="see-also"></a>Voir aussi  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)

