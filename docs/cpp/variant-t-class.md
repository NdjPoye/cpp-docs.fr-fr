---
title: _variant_t (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Variant
- _variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class, operators
- _variant_t class
- _variant_t class, member functions
- VARIANT object
- VARIANT object, COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 10
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3c074061955adbb1682bb7d96345a31fcf8f04e7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="variantt-class"></a>_variant_t (classe)
**Section spécifique à Microsoft**  
  
 A `_variant_t` objet encapsule le `VARIANT` type de données. La classe gère l’allocation des ressources et la désallocation et effectue des appels de fonction à **VariantInit** et **VariantClear** selon le cas.  
  
### <a name="construction"></a>Construction  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|Construit un objet `_variant_t`.|  
  
### <a name="operations"></a>Opérations  
  
|||  
|-|-|  
|[Attacher](../cpp/variant-t-attach.md)|Attache un **VARIANT** de l’objet dans le `_variant_t` objet.|  
|[Effacer](../cpp/variant-t-clear.md)|Efface encapsulé **VARIANT** objet.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Modifie le type de la `_variant_t` objet au **VARTYPE**.|  
|[Détacher](../cpp/variant-t-detach.md)|Détache encapsulé **VARIANT** objet à partir de ce `_variant_t` objet.|  
|[SetString](../cpp/variant-t-setstring.md)|Assigne une chaîne à cet objet `_variant_t`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[Opérateur =](../cpp/variant-t-operator-equal.md)|Assigne une nouvelle valeur à un objet `_variant_t` existant.|  
|[opérateur ==, ! =](../cpp/variant-t-relational-operators.md)|Comparez deux objets `_variant_t` pour déterminer leur égalité ou inégalité.|  
|[Extracteurs](../cpp/variant-t-extractors.md)|Extraire des données d’encapsulé **VARIANT** objet.|  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** comutil.h  
  
 **Lib :** comsuppw.lib ou comsuppwd.lib (consultez [/Zc : wchar_t (wchar_t est un Type natif)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour plus d’informations)  
  
## <a name="see-also"></a>Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)
