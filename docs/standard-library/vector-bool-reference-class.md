---
title: vector&lt;bool&gt;::reference, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vector<bool>::reference
- std::vector<bool>::reference
dev_langs:
- C++
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: 22
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 0a4ec7d943ab478ba36a48e8b44ac915ba1c3893
ms.lasthandoff: 02/24/2017

---
# <a name="vectorltboolgtreference-class"></a>vector&lt;bool&gt;::reference, classe
La classe `vector<bool>::reference` est une classe proxy fournie par la [classe vector\<bool>](../standard-library/vector-bool-class.md) pour simuler `bool&`.  
  
## <a name="remarks"></a>Notes  
 Une référence simulée est requise car C++ n'autorise pas en mode natif les références directes aux bits. `vector<bool>` utilise un seul bit par élément, lequel peut être référencé à l'aide de cette classe proxy. Toutefois, la simulation de référence n'est pas terminée car certaines attributions ne sont pas valides. Par exemple, comme l’adresse de l’objet `vector<bool>::reference` ne peut pas être prise, le code suivant qui utilise [vector\<bool>::operator&#91;&#93;](http://msdn.microsoft.com/Library/97738633-690d-4069-b2d9-8c54104fbfdd) n’est pas correct :  
  
```cpp  
vector<bool> vb;  
// ...  
bool* pb = &vb[1]; // conversion error - do not use  
bool& refb = vb[1];   // conversion error - do not use  
```  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|Inverse la valeur booléenne d'un élément de vecteur.|  
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|Fournit une conversion implicite de `vector<bool>::reference` en `bool`.|  
|[operator=](../standard-library/vector-bool-reference-operator-assign.md)|Assigne une valeur booléenne à un bit, ou la valeur détenue par un élément référencé à un bit.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête** : \<vector>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<vector>](../standard-library/vector.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)


