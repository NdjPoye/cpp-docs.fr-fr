---
title: _variant_t::ChangeType | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53fd73fc9606053dda6f8c143618373ad9bb7e4e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
  
## <a name="remarks"></a>Notes  
 Cette fonction membre convertit un `_variant_t` objet indiqué **VARTYPE**. Si `pSrc` est **NULL**, la conversion s’effectue sur place, sinon cet `_variant_t` objet est copié à partir de `pSrc` , puis converti.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)