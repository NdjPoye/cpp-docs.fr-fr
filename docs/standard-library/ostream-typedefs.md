---
title: '&lt;ostream&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: bcf7df720a9b3a71ddbb32bd6eeb73f2f1332391
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt;, typedefs
|||  
|-|-|  
|[ostream](#ostream)|[wostream](#wostream)|  
  
##  <a name="ostream"></a>  ostream  
 Crée un type à partir de basic_ostream qui est spécialisé sur `char`, et `char_traits` spécialisé sur `char`.  
  
```
typedef basic_ostream<char, char_traits<char>> ostream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ostream](../standard-library/basic-ostream-class.md) qui est spécialisé pour les éléments de type `char` ayant les caractéristiques de caractère par défaut.  
  
##  <a name="wostream"></a>  wostream  
 Crée un type à partir de basic_ostream qui est spécialisé sur `wchar_t`, et `char_traits` spécialisé sur `wchar_t`.  
  
```
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ostream](../standard-library/basic-ostream-class.md) qui est spécialisé pour les éléments de type `wchar_t` ayant les caractéristiques de caractère par défaut.  
  
## <a name="see-also"></a>Voir aussi  
 [\<ostream>](../standard-library/ostream.md)




