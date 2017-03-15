---
title: Classe de CComEnum | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
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
ms.openlocfilehash: 72c172d7a619bb4fd1bd265e465653b691c0bc7b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenum-class"></a>CComEnum (classe)
Cette classe définit un objet d’énumérateur COM basé sur un tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>  
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
 T,
    Copy>,
 public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>Paramètres  
 `Base`  
 Un énumérateur COM ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) interface.  
  
 `piid`  
 Pointeur vers l’ID de l’interface de l’énumérateur.  
  
 `T`  
 Le type d’élément exposé par l’interface de l’énumérateur.  
  
 `Copy`  
 Un homogènes [copier la classe de stratégie](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 Le modèle de thread de la classe. Ce paramètre par défaut pour le modèle de thread d’objet global utilisé dans votre projet.  
  
## <a name="remarks"></a>Remarques  
 `CComEnum`définit un objet d’énumérateur COM basé sur un tableau. Cette classe est analogue à [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) qui implémente un énumérateur basé sur un conteneur de bibliothèque C++ Standard. Procédure standard d’utilisation de cette classe est décrites ci-dessous. Pour plus d’informations, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>Pour utiliser cette classe :  
  
- `typedef`une spécialisation de cette classe.  
  
-   Utilisez le `typedef` comme argument dans une spécialisation de modèle `CComObject`.  
  
-   Créez une instance de la `CComObject` spécialisation.  
  
-   Initialiser l’objet énumérateur en appelant [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   L’interface de l’énumérateur de retour au client.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
## <a name="example"></a>Exemple  
 Le code ci-dessous fournit une fonction réutilisable pour la création et l’initialisation d’un objet énumérateur.  
  
 [!code-cpp[NVC_ATL_COM N°&32;](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Cette fonction de modèle peut être utilisée pour implémenter le `_NewEnum` propriété d’une interface de collection, comme indiqué ci-dessous :  
  
 [!code-cpp[NVC_ATL_COM&#33;](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Ce code crée un `typedef` pour `CComEnum` qui expose un vecteur de **variante**s via le **IEnumVariant** interface. Le **CVariantArrayCollection** classe spécialisée simplement **CreateEnumerator** pour travailler avec des objets d’énumérateur de ce type et la transmet les arguments nécessaires.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [CComEnumImpl (classe)](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx (classe)](../../atl/reference/ccomobjectrootex-class.md)

