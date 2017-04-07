---
title: Classe CComPtr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
dev_langs:
- C++
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
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
ms.openlocfilehash: ae7bb5e85f23492bdbef4af86d9f68fa83c991e2
ms.lasthandoff: 02/24/2017

---
# <a name="ccomptr-class"></a>Classe CComPtr
Une classe de pointeur intelligent pour la gestion des pointeurs d’interface COM.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>  
class CComPtr
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Une interface COM qui spécifie le type de pointeur à stocker.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComPtr::CComPtr](#ccomptr)|Constructeur.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComPtr::operator =](#operator_eq)|Assigne un pointeur vers le pointeur de membre.|  
  
## <a name="remarks"></a>Notes  
 ATL utilise `CComPtr` et [CComQIPtr](../../atl/reference/ccomqiptr-class.md) pour gérer les pointeurs d’interface COM. Tous deux sont dérivés de [CComPtrBase](../../atl/reference/ccomptrbase-class.md), et tous deux effectuant le comptage de références automatique.  
  
 Le **CComPtr** et [CComQIPtr](../../atl/reference/ccomqiptr-class.md) classes peuvent aider à éliminer les fuites de mémoire en effectuant le décompte de références automatique.  Les fonctions suivantes à la fois effectuent les mêmes opérations logiques ; Toutefois, notez comment la deuxième version peut être moins sujette aux erreurs à l’aide de la **CComPtr** classe :  
  
 [!code-cpp[NVC_ATL_Utilities&#130;](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities&#131;](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]  
  
 Dans les versions Debug, lier atlsd.lib pour le suivi du code.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="ccomptr"></a>CComPtr::CComPtr  
 Constructeur.  
  
```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```  
  
### <a name="parameters"></a>Paramètres  
 `lp`  
 Utilisé pour initialiser le pointeur d’interface.  
  
 `T`  
 Une interface COM.  
  
##  <a name="operator_eq"></a>CComPtr::operator =  
 Opérateur d'assignation.  
  
```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers la mise à jour `CComPtr` objet  
  
### <a name="remarks"></a>Notes  
 Cette opération AddRefs le nouvel objet et versions de l’objet existant, s’il existe.  
  
## <a name="see-also"></a>Voir aussi  
 [CComPtr::CComPtr](#ccomptr)   
 [CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

