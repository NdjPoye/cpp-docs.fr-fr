---
title: '&lt;istream&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e3607735f989b61f373eb689b8fe3b2dee656f7b
ms.lasthandoff: 02/24/2017

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


