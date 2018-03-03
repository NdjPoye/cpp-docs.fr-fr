---
title: Comptrref, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b1bbe134f15fdba6863f1725cbcc7effcb6d94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrref-class"></a>ComPtrRef (classe)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 A [ComPtr\<T >](../windows/comptr-class.md) type ou un type dérivé, pas simplement l’interface représentée par le ComPtr.  
  
## <a name="remarks"></a>Notes  
 Représente une référence à un objet de type ComPtr\<T >.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[ComPtrRef::ComPtrRef, constructeur](../windows/comptrref-comptrref-constructor.md)|Initialise une nouvelle instance de la classe ComPtrRef à partir du pointeur spécifié vers un autre objet ComPtrRef.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ComPtrRef::GetAddressOf, méthode](../windows/comptrref-getaddressof-method.md)|Récupère l’adresse d’un pointeur vers l’interface représentée par l’objet ComPtrRef en cours.|  
|[ComPtrRef::ReleaseAndGetAddressOf, méthode](../windows/comptrref-releaseandgetaddressof-method.md)|Supprime l’objet ComPtrRef actuel et retourne un pointeur-à-un en pointeur vers l’interface qui a été représenté par l’objet ComPtrRef.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType**, opérateur](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Supprime l’objet ComPtrRef actuel et retourne un pointeur-à-un en pointeur vers l’interface qui a été représenté par l’objet ComPtrRef.|  
|[ComPtrRef::operator T*, opérateur](../windows/comptrref-operator-t-star-operator.md)|Retourne la valeur de la [ptr_](../windows/comptrrefbase-ptr-data-member.md) membre de données de l’objet ComPtrRef en cours.|  
|[ComPtrRef::operator void**, opérateur](../windows/comptrref-operator-void-star-star-operator.md)|Supprime l’objet ComPtrRef actif, convertit le pointeur vers l’interface qui a été représenté par l’objet ComPtrRef comme un pointeur à pointeur-à `void`, puis retourne le pointeur de cast.|  
|[ComPtrRef::operator*, opérateur](../windows/comptrref-operator-star-operator.md)|Récupère le pointeur vers l’interface représentée par l’objet ComPtrRef en cours.|  
|[ComPtrRef::operator==, opérateur](../windows/comptrref-operator-equality-operator.md)|Indique si deux objets ComPtrRef sont égaux.|  
|[ComPtrRef::operator!=, opérateur](../windows/comptrref-operator-inequality-operator.md)|Indique si deux objets ComPtrRef ne sont pas égaux.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** client.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)