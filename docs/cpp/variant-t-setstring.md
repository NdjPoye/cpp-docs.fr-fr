---
title: _variant_t::SetString | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _variant_t::SetString
dev_langs: C++
helpviewer_keywords: SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c433aafbe9799486d141e04ca747cbb4f7c3e22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Section spécifique à Microsoft**  
  
 Assigne une chaîne à cet objet `_variant_t`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pSrc`  
 Pointeur vers la chaîne de caractères.  
  
## <a name="remarks"></a>Notes  
 Convertit une chaîne de caractères ANSI en chaîne Unicode `BSTR` et l'assigne à cet objet `_variant_t`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)