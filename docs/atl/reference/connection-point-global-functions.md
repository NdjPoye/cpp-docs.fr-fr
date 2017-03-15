---
title: Fonctions globales de Point de connexion | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8271f512141e4d2cc274d180b31e1ad33bfc354e
ms.lasthandoff: 02/24/2017

---
# <a name="connection-point-global-functions"></a>Fonctions globales de Point de connexion
Ces fonctions fournissent la prise en charge des points de connexion et le récepteur de cartes.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|Crée une connexion entre le point de connexion d'un objet et le récepteur d'un client.|  
|[AtlUnadvise](#atlunadvise)|Met fin à la connexion établie via `AtlAdvise`.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|Conseille ou avertit les entrées dans une table de récepteur d’événements.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
   
##  <a name="a-nameatladvisea--atladvise"></a><a name="atladvise"></a>AtlAdvise  
 Crée une connexion entre le point de connexion d'un objet et le récepteur d'un client.  
  
> [!IMPORTANT]
>  Cette fonction ne peut pas être utilisée dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```  
  
### <a name="parameters"></a>Paramètres  
 `pUnkCP`  
 [in] Un pointeur vers le **IUnknown** de l’objet, le client souhaite se connecter avec.  
  
 *pUnk*  
 [in] Un pointeur vers du client **IUnknown**.  
  
 `iid`  
 [in] Le GUID du point de connexion. En règle générale, cela est identique à l’interface sortante gérée par le point de connexion.  
  
 `pdw`  
 [out] Pointeur vers le cookie qui identifie de façon unique la connexion.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="remarks"></a>Notes  
 Le récepteur implémente l’interface sortante est pris en charge par le point de connexion. Le client utilise le `pdw` cookie pour supprimer la connexion en le passant à [AtlUnadvise](#atlunadvise).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#91;](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="a-nameatlunadvisea--atlunadvise"></a><a name="atlunadvise"></a>AtlUnadvise  
 Met fin à la connexion établie via [AtlAdvise](#atladvise).  
  
> [!IMPORTANT]
>  Cette fonction ne peut pas être utilisée dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>Paramètres  
 `pUnkCP`  
 [in] Un pointeur vers le **IUnknown** de l’objet auquel le client est connecté avec.  
  
 `iid`  
 [in] Le GUID du point de connexion. En règle générale, cela est identique à l’interface sortante gérée par le point de connexion.  
  
 `dw`  
 [in] Cookie qui identifie de façon unique la connexion.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#96;](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="a-nameatladvisesinkmapa--atladvisesinkmap"></a><a name="atladvisesinkmap"></a>AtlAdviseSinkMap  
 Appelez cette fonction pour conseiller ou déconseiller toutes les entrées de la table d'événements du récepteur de l'objet.  
  
> [!IMPORTANT]
>  Cette fonction ne peut pas être utilisée dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>Paramètres  
 *pT*  
 [in] Pointeur vers l’objet qui contient la table de récepteur.  
  
 `bAdvise`  
 [in] **true** si toutes les entrées de récepteur sont d’être informé ; **false** si toutes les entrées de récepteur doivent être cessent d’être averties.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#92;](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)   
 [Macros de Point de connexion](../../atl/reference/connection-point-macros.md)

