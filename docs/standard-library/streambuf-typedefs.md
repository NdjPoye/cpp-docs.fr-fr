---
title: '&lt;streambuf&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 932b5ce7a664f75eb92f19fdbf32363b9300fb09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt;, typedefs
|||  
|-|-|  
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|  
  
##  <a name="streambuf"></a>  streambuf  
 Spécialisation de `basic_streambuf` qui utilise `char` comme paramètres du modèle.  
  
```
typedef basic_streambuf<char, char_traits<char>> streambuf;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_streambuf](../standard-library/basic-streambuf-class.md), spécialisée pour les éléments de type `char` ayant les traits de caractère par défaut.  
  
##  <a name="wstreambuf"></a>  wstreambuf  
 Spécialisation de `basic_streambuf` qui utilise `wchar_t` comme paramètres du modèle.  
  
```
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_streambuf](../standard-library/basic-streambuf-class.md), spécialisée pour les éléments de type `wchar_t` ayant les traits de caractère par défaut.  
  
## <a name="see-also"></a>Voir aussi  
 [\<streambuf>](../standard-library/streambuf.md)



