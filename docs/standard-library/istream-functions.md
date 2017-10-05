---
title: '&lt;istream&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: da4b05286c56bf809914b142a254a311f8655ce9
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt;, fonction
|||  
|-|-|  
|[swap](#istream_swap)|[ws](#ws)|  
  
##  <a name="istream_swap"></a>  swap  
 Échange les éléments de deux objets de flux.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_istream<Elem, Tr>& left,  
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>  
void swap(
    basic_iostream<Elem, Tr>& left,  
    basic_iostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `left`  
 Flux.  
  
 `right`  
 Flux.  
  
##  <a name="ws"></a>  ws  
 Ignore l'espace blanc dans le flux.  
  
```  
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Istr`  
 Un flux.  
  
### <a name="return-value"></a>Valeur de retour  
 flux.  
  
### <a name="remarks"></a>Notes  
 Le manipulateur extrait et ignore tout élément `ch` pour lequel [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **Elem**> >( [getloc](../standard-library/ios-base-class.md#getloc)). **is**( **ctype**\< **Elem**>:: **space**, **ch**) a la valeur true.  
  
 La fonction appelle [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) si elle rencontre la fin du fichier pendant l’extraction d’éléments. Il retourne `_Istr`.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation de `ws`, consultez [operator>>](../standard-library/istream-operators.md#op_gt_gt).  
  
## <a name="see-also"></a>Voir aussi  
 [\<istream>](../standard-library/istream.md)


