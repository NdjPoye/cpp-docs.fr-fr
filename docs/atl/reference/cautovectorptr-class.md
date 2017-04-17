---
title: Classe de CAutoVectorPtr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
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
ms.openlocfilehash: bb4bbd110552d1e3cf604add44de7e428d2703ee
ms.lasthandoff: 02/24/2017

---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr (classe)
Cette classe représente un objet pointeur intelligent à l’aide de nouveau vecteur et supprimer des opérateurs.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename T>  
class CAutoVectorPtr
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de pointeur.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Constructeur.|  
|[CAutoVectorPtr :: ~ CAutoVectorPtr](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::Allocate](#allocate)|Appelez cette méthode pour allouer la mémoire requise par le tableau d’objets pointés par `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](#attach)|Appelez cette méthode pour prendre possession d’un pointeur existant.|  
|[CAutoVectorPtr::Detach](#detach)|Appelez cette méthode pour libérer la possession d’un pointeur.|  
|[CAutoVectorPtr::Free](#free)|Appelez cette méthode pour supprimer un objet vers lequel pointé un `CAutoVectorPtr`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::operator T *](#operator_t__star)|L’opérateur de cast.|  
|[CAutoVectorPtr::operator =](#operator_eq)|L’opérateur d’assignation.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::m_p](#m_p)|La variable de membre de données de pointeur.|  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit des méthodes pour créer et gérer un pointeur intelligent, ce qui vous permettra de protéger contre les fuites de mémoire en libérant les ressources d’automatiquement lorsqu’elle se trouve hors de portée. `CAutoVectorPtr`est semblable à `CAutoPtr`, la seule différence étant que `CAutoVectorPtr` utilise [vector new []](../../standard-library/new-operators.md#operator_new_arr) et [vecteur delete []](../../standard-library/new-operators.md#operator_delete_arr) pour allouer et libérer de la mémoire au lieu de C++ **nouveau** et **supprimer** opérateurs. Consultez la page [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) si les classes de collection de `CAutoVectorPtr` sont requis.  

  
 Consultez la page [CAutoPtr](../../atl/reference/cautoptr-class.md) pour obtenir un exemple d’utilisation d’une classe de pointeur intelligent.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="allocate"></a>CAutoVectorPtr::Allocate  
 Appelez cette méthode pour allouer la mémoire requise par le tableau d’objets pointés par `CAutoVectorPtr`.  
  
```
bool Allocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nElements`  
 Nombre d’éléments dans le tableau.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la mémoire est correctement alloué, false en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Dans les versions debug, un échec d’assertion se produit si le [CAutoVectorPtr::m_p](#m_p) variable membre pointe actuellement à une valeur ; autrement dit, il n’est pas égal à NULL.  
  
##  <a name="attach"></a>CAutoVectorPtr::Attach  
 Appelez cette méthode pour prendre possession d’un pointeur existant.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Le `CAutoVectorPtr` objet prendra possession de ce pointeur.  
  
### <a name="remarks"></a>Notes  
 Lorsqu’un `CAutoVectorPtr` objet prend possession du pointeur, il supprime automatiquement le pointeur et les données allouées lorsqu’il devient hors de portée. Si [CAutoVectorPtr::Detach](#detach) est appelée, le programmeur à nouveau avec la responsabilité de libérer les ressources est alloué.  
  
 Dans les versions debug, un échec d’assertion se produit si le [CAutoVectorPtr::m_p](#m_p) variable membre pointe actuellement à une valeur ; autrement dit, il n’est pas égal à NULL.  
  
##  <a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr  
 Constructeur.  
  
```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Un pointeur existant.  
  
### <a name="remarks"></a>Remarques  
 Le `CAutoVectorPtr` objet peut être créé à l’aide d’un pointeur existant, auquel cas il transfère la propriété du pointeur.  
  
##  <a name="dtor"></a>CAutoVectorPtr :: ~ CAutoVectorPtr  
 Destructeur.  
  
```
~CAutoVectorPtr() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources allouées. Appels [CAutoVectorPtr::Free](#free).  
  
##  <a name="detach"></a>CAutoVectorPtr::Detach  
 Appelez cette méthode pour libérer la possession d’un pointeur.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une copie du pointeur.  
  
### <a name="remarks"></a>Notes  
 Libère la possession d’un pointeur, définit les [CAutoVectorPtr::m_p](#m_p) variable de membre avec la valeur NULL et retourne une copie du pointeur. Après avoir appelé **détachement**, il jusqu’au programmeur pour libérer les ressources est allouée sur laquelle le `CAutoVectorPtr` objet peut avoir précédemment la responsabilité.  
  
##  <a name="free"></a>CAutoVectorPtr::Free  
 Appelez cette méthode pour supprimer un objet vers lequel pointé un `CAutoVectorPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Notes  
 L’objet pointé par le `CAutoVectorPtr` est libéré et la [CAutoVectorPtr::m_p](#m_p) variable membre a la valeur NULL.  
  
##  <a name="m_p"></a>CAutoVectorPtr::m_p  
 La variable de membre de données de pointeur.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Notes  
 Cette variable membre conserve les informations de pointeur.  
  
##  <a name="operator_eq"></a>CAutoVectorPtr::operator =  
 L’opérateur d’assignation.  
  
```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Un pointeur.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à un **CAutoVectorPtr\< T >**.  
  
### <a name="remarks"></a>Remarques  
 Détache de l’opérateur d’assignation de la `CAutoVectorPtr` objet à partir de n’importe quel pointeur actuel et attache le nouveau pointeur, `p`, à la place.  
  
##  <a name="operator_t__star"></a>CAutoVectorPtr::operator T *  
 L’opérateur de cast.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Retourne un pointeur vers le type de données objet défini dans le modèle de classe.  
  
## <a name="see-also"></a>Voir aussi  
 [CAutoPtr (classe)](../../atl/reference/cautoptr-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
