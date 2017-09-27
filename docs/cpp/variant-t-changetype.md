---
title: _variant_t::ChangeType | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method
- VARIANT object, ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
caps.latest.revision: 6
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
ms.openlocfilehash: 535bc332a108cf50badca116c496661b7c257bf7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Section spécifique à Microsoft**  
  
 Modifie le type de la `_variant_t` objet au **VARTYPE**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `vartype`  
 Le **VARTYPE** pour ce `_variant_t` objet.  
  
 `pSrc`  
 Pointeur vers l'objet `_variant_t` à convertir. Si cette valeur est **NULL**, conversion s’effectue sur place.  
  
## <a name="remarks"></a>Remarques  
 Cette fonction membre convertit un `_variant_t` objet indiqué **VARTYPE**. Si `pSrc` est **NULL**, la conversion s’effectue sur place, sinon cet `_variant_t` objet est copié à partir de `pSrc` , puis converti.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)
