---
title: "&lt;allocators&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 0a2da6c72e8900c0cea86c30c6b8511e6b256ff9
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt;, opérateurs
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 Vérifie l'inégalité entre les objets allocateurs d'une classe spécifiée.  
  
```
template <class Type, class Sync>  
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Un des objets allocateur dont l’inégalité doit être vérifiée.|  
|`right`|Un des objets allocateur dont l’inégalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets allocateur ne sont pas égaux ; **false** si les objets allocateur sont égaux.  
  
### <a name="remarks"></a>Notes  
 L’opérateur de modèle retourne `!(left == right)`.  
  
##  <a name="op_eq_eq"></a>  operator==  
 Vérifie l'égalité entre les objets allocateurs d'une classe spécifiée.  
  
```
template <class Type, class Sync>  
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Un des objets allocateur dont l’égalité doit être vérifiée.|  
|`right`|Un des objets allocateur dont l’égalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets allocateur sont égaux ; **false** si les objets allocateur ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 Cet opérateur de modèle retourne `left.equals(right)`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)




