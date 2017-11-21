---
title: Classe de CAtlWinModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
dev_langs: C++
helpviewer_keywords: CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 59f555f129548b3ced008b61364fa4a9900e062d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="catlwinmodule-class"></a>Classe de CAtlWinModule
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
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Retourne un pointeur vers l’objet de données de module de fenêtre.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe prend en charge toutes les classes ATL qui nécessitent les fonctionnalités de fenêtrage.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)  
  
 `CAtlWinModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData  
 Cette méthode initialise et ajoute un `_AtlCreateWndData` structure.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pData`  
 Pointeur vers le `_AtlCreateWndData` structure devant être initialisé et ajoutées au module actuel.  
  
 `pObject`  
 Pointeur vers un objet **cela** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode appelle [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) qui initialise un [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) structure. Cette structure stockera la **cela** pointeur, permet d’obtenir l’instance de classe dans les procédures de fenêtre.  
  
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
  
### <a name="remarks"></a>Remarques  
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
