---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec0407c413c44e5ca7778940dd51d8e776bfc687
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
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
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<vector>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [vector\<bool>::reference, classe](../standard-library/vector-bool-reference-class.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)

