---
title: nothrow_t, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: nothrow_t
dev_langs: C++
helpviewer_keywords: nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 46c58f637123d140372ba368afa7a26ba17b3f94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="nothrowt-structure"></a>nothrow_t, structure
Le struct est utilisé comme paramètre de fonction de l’opérateur new pour indiquer que la fonction doit retourner un pointeur null pour signaler un échec d’allocation, au lieu de lever une exception.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct std::nothrow_t {};
```  
  
## <a name="remarks"></a>Remarques  
 Le struct aide le compilateur à sélectionner la version correcte du constructeur. [nothrow](../standard-library/new-functions.md#nothrow) est un synonyme des objets de type `std::nothrow_t`.  
  
## <a name="example"></a>Exemple  
 Pour obtenir des exemples d’utilisation de `std::nothrow_t` comme paramètre de fonction, consultez [new, opérateur](../standard-library/new-operators.md#op_new) et [new &#91;&#93;, opérateur](../standard-library/new-operators.md#op_new_arr).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<new>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


