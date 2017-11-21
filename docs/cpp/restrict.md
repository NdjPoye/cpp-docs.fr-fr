---
title: restreindre | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: restrict_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9176336ac96d88a34d758fd55c09a3a938f371fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="restrict"></a>restrict
**Section spécifique à Microsoft**  
  
 Appliqué à une déclaration ou une définition de fonction qui retourne un type pointeur et indique au compilateur que la fonction retourne un objet qui n'aura pas comme alias un autre pointeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__declspec(restrict) return_type f();  
```  
  
## <a name="remarks"></a>Remarques  
 Le compilateur propage `__declspec(restrict)`. Par exemple, la fonction CRT `malloc` est décorée avec `__declspec(restrict)`. Par conséquent, les pointeurs initialisés à des emplacements de mémoire avec `malloc` sont également supposés ne pas avoir d'alias.  
  
 Le compilateur ne vérifie pas que le pointeur n'a pas réellement d'alias. Il incombe au développeur de s'assurer que le programme n'attribue pas d'alias à un pointeur marqué avec le modificateur `restrict __declspec`.  
  
 Pour une sémantique similaire sur les variables, consultez [__restrict](../cpp/extension-restrict.md).  
  
## <a name="example"></a>Exemple  
 Consultez [noalias](../cpp/noalias.md) pour un exemple en utilisant `restrict`.  
  
 Pour plus d’informations sur le mot clé restrict qui fait partie de C++ AMP, consultez [restrict (C++ AMP)](../cpp/restrict-cpp-amp.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)