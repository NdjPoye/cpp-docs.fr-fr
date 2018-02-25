---
title: '&lt;istream&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 866950a000556392a9c44122c32775e0f9d59422
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt;, typedefs
||||  
|-|-|-|  
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|  
|[wistream](#wistream)|  
  
##  <a name="iostream"></a>  iostream  
 Type `basic_iostream` spécialisé sur `char`.  
  
```  
typedef basic_iostream<char, char_traits<char>> iostream;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_iostream](../standard-library/basic-iostream-class.md), spécialisé pour les éléments de type `char` ayant les caractéristiques par défaut.  
  
##  <a name="istream"></a>  istream  
 Type `basic_istream` spécialisé sur `char`.  
  
```  
typedef basic_istream<char, char_traits<char>> istream;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_istream](../standard-library/basic-istream-class.md), spécialisé pour les éléments de type `char` ayant les caractéristiques par défaut.  
  
##  <a name="wiostream"></a>  wiostream  
 Type `basic_iostream` spécialisé sur `wchar_t`.  
  
```  
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_iostream](../standard-library/basic-iostream-class.md), spécialisé pour les éléments de type `wchar_t` ayant les caractéristiques par défaut.  
  
##  <a name="wistream"></a>  wistream  
 Type `basic_istream` spécialisé sur `wchar_t`.  
  
```  
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_istream](../standard-library/basic-istream-class.md), spécialisé pour les éléments de type `wchar_t` ayant les caractéristiques par défaut.  
  
## <a name="see-also"></a>Voir aussi  
 [\<istream>](../standard-library/istream.md)

