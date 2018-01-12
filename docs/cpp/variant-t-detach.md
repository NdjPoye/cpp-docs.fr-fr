---
title: _variant_t::Detach | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs: C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 577b4874dd6d89c0c6c60b1a7981e74944e77ba8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Section spécifique à Microsoft**  
  
 Détache encapsulé **VARIANT** objet à partir de ce `_variant_t` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Encapsulé **variante**.  
  
## <a name="remarks"></a>Notes  
 Extrait et retourne encapsulé **VARIANT**, puis efface alors cet `_variant_t` objet sans le détruire. Cette fonction membre supprime le **VARIANT** d’encapsulation et définit les **VARTYPE** de ce `_variant_t` objet `VT_EMPTY`. C’est à vous permettre de libérer retourné **VARIANT** en appelant le [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) (fonction).  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)