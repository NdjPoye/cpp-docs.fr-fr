---
title: _variant_t::Attach | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 33e21d3bea71c80b8b60df222682fda560fbce9c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="varianttattach"></a>_variant_t::Attach
**Section spécifique à Microsoft**  
  
 Attache un **VARIANT** de l’objet dans le `_variant_t` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *varSrc*  
 A **VARIANT** à attacher à cet objet `_variant_t` objet.  
  
## <a name="remarks"></a>Remarques  
 Prend possession de la **VARIANT** en l’encapsulant. Cette fonction membre libère tout encapsulé existant **VARIANT**, puis copie fourni **VARIANT**et définit sa **VARTYPE** à `VT_EMPTY` pour vous assurer sa ressources peuvent être libérées uniquement par le `_variant_t` destructeur.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)
