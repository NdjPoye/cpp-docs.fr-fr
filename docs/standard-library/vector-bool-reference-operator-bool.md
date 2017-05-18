---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: acc0ecd4edaf1e58977dcbdeb483d497a72bc4c8
ms.openlocfilehash: f79b54237aa3a3b53000aaa47ef6a8e198ed6725
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool
Fournit une conversion implicite de `vector<bool>::reference` en `bool`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
operator bool() const;
```  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur booléenne de l’élément de l’objet [vector\<bool>](../standard-library/vector-bool-class.md).  
  
## <a name="remarks"></a>Notes  
 L'objet `vector<bool>` ne peut pas être modifié par cet opérateur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<vector>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [vector\<bool>::reference, classe](../standard-library/vector-bool-reference-class.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)


