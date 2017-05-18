---
title: "C2429 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 9
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
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 7d2c27ccdba28720596984c46c9d24f9d29c7b15
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2429"></a>C2429 d’erreur du compilateur
«*fonctionnalité de langage*« requiert l’indicateur de compilateur »*option du compilateur*»  
  
La fonctionnalité de langage nécessite une option de compilateur spécifique de prise en charge.  
  
L’erreur C2429 : fonctionnalité de langage 'imbriqué-namespace-definition' requiert l’indicateur de compilateur « / std:c ++ dernière » est générée si vous essayez de définir un *espace de noms composé*, un espace de noms qui contient un ou plusieurs noms d’espace de noms étendue imbriquée, depuis Visual Studio 2015 Update 3. Composés d’espace de noms définitions ne sont pas autorisées en C++ avant C ++&17;. Le compilateur prend en charge les définitions d’espace de noms composés lors de la [/std:c ++ dernières](../../build/reference/std-specify-language-standard-version.md) option du compilateur est spécifiée :  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
