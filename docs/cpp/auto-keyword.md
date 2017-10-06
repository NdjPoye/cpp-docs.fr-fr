---
title: "auto, mot clé | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- auto_cpp
dev_langs:
- C++
helpviewer_keywords:
- automatic storage class [C++], auto keyword
- auto keyword [C++]
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0413fd47b486cf1613b7c249b93e6a3507a5577c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="auto-keyword"></a>auto, mot clé
Le mot clé `auto` est un spécificateur de déclaration. Cependant, le code C++ standard définit une signification originale et modifiée pour ce mot clé . Avant Visual C++ 2010, le `auto` mot clé déclare une variable dans le *automatique* classe de stockage ; autrement dit, une variable qui a une durée de vie locale. Depuis Visual C++ 2010, le `auto` mot clé déclare une variable dont le type est déduit à partir de l’expression d’initialisation dans sa déclaration. Le [/Zc : auto &#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md) option du compilateur contrôle la signification de la `auto` (mot clé).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>Remarques  
 La définition du mot clé `auto` change dans le langage de programmation C++, mais pas dans le langage de programmation C.  
  
 Les rubriques suivantes décrivent le mot clé `auto` et l'option du compilateur correspondante :  
  
-   [Auto](../cpp/auto-cpp.md) décrit la nouvelle définition de la `auto` (mot clé).  
  
  
-   [/ Zc : auto (déduire le Type de Variable)](../build/reference/zc-auto-deduce-variable-type.md) décrit l’option du compilateur qui indique au compilateur de la définition du `auto` mot clé à utiliser.  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)
