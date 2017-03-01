---
title: '&lt;ostream&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 310954b0965be071c288f09de058e3cebe3ce27d
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt;, typedefs
|||  
|-|-|  
|[ostream](#ostream)|[wostream](#wostream)|  
  
##  <a name="a-nameostreama--ostream"></a><a name="ostream"></a>  ostream  
 Crée un type à partir de basic_ostream qui est spécialisé sur `char`, et `char_traits` spécialisé sur `char`.  
  
```
typedef basic_ostream<char, char_traits<char>> ostream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ostream](../standard-library/basic-ostream-class.md) qui est spécialisé pour les éléments de type `char` ayant les caractéristiques de caractère par défaut.  
  
##  <a name="a-namewostreama--wostream"></a><a name="wostream"></a>  wostream  
 Crée un type à partir de basic_ostream qui est spécialisé sur `wchar_t`, et `char_traits` spécialisé sur `wchar_t`.  
  
```
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ostream](../standard-library/basic-ostream-class.md) qui est spécialisé pour les éléments de type `wchar_t` ayant les caractéristiques de caractère par défaut.  
  
## <a name="see-also"></a>Voir aussi  
 [\<ostream>](../standard-library/ostream.md)




