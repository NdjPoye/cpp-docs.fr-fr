---
title: Classe de CWinTraitsOR | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CWinTraitsOR
- ATL::CWinTraitsOR
- CWinTraitsOR
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cd077c7f79c3099d0e825a48233e7a8b269c0d04
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraitsor-class"></a>CWinTraitsOR (classe)
Cette classe fournit une méthode pour standardiser les styles utilisés lors de la création d’un objet window.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```  
  
#### <a name="parameters"></a>Paramètres  
 `t_dwStyle`  
 Styles de fenêtre par défaut.  
  
 `t_dwExStyle`  
 Valeur par défaut des styles de fenêtre étendus.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Récupère les styles étendus pour le `CWinTraitsOR` objet.|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Récupère les styles standards pour la `CWinTraitsOR` objet.|  
  
## <a name="remarks"></a>Remarques  
 Cela [traits de fenêtre](../../atl/understanding-window-traits.md) classe fournit une méthode simple pour standardiser les styles utilisés pour la création d’un objet fenêtre ATL. Utiliser une spécialisation de cette classe comme un paramètre de modèle [CWindowImpl](../../atl/reference/cwindowimpl-class.md) ou l’autre des classes de fenêtre ATL pour spécifier l’ensemble minimal de styles standard et à utiliser pour les instances de cette classe de fenêtre.  
  
 Utiliser une spécialisation de ce modèle si vous souhaitez vous assurer que certains styles sont définis pour toutes les instances de la classe de fenêtre tout en autorisant les autres styles à définir sur une base par instance dans l’appel à [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Si vous souhaitez fournir par défaut des styles de fenêtre qui seront utilisées uniquement si aucun style n’est spécifié dans l’appel à `CWindowImpl::Create`, utilisez [CWinTraits](../../atl/reference/cwintraits-class.md) à la place.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="a-namegetwndstylea--cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 Appelez cette fonction pour récupérer une combinaison (à l’aide de l’opérateur OR logique) de styles standards de la `CWinTraits` objet et les styles par défaut spécifiés par `t_dwStyle`.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Styles utilisés pour la création d’une fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 Une combinaison de styles sont passés dans `dwStyle` et la valeur par défaut que ceux spécifiés par `t_dwStyle`, à l’aide de l’opérateur OR logique.  
  
##  <a name="a-namegetwndexstylea--cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 Appelez cette fonction pour récupérer une combinaison (à l’aide de l’opérateur OR logique) de styles étendus de la `CWinTraits` objet et les styles par défaut spécifiés par `t_dwStyle`.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwExStyle`  
 Styles étendus utilisés pour la création d’une fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 Une combinaison de styles étendus qui sont passés dans `dwExStyle` et par défaut que ceux spécifiés par `t_dwExStyle`, à l’aide de l’opérateur OR logique  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Comprendre les caractéristiques de fenêtre](../../atl/understanding-window-traits.md)


