---
title: Compilateur avertissement (niveau 1) C4342 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4342
dev_langs:
- C++
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
caps.latest.revision: 10
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: c4a2afbc3ced186b0db63b22b3cc5c2b27204c71
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4342"></a>Avertissement du compilateur (niveau 1) C4342
changement de comportement : '*fonction*' appelé, mais un opérateur de membre a été appelé dans les versions précédentes  
  
 Dans les versions de Visual C++ antérieures à Visual Studio 2002, un membre a été appelé, mais ce comportement a été modifié et le compilateur recherche désormais la meilleure correspondance dans la portée espace de noms.  
  
 Si un opérateur de membre a été trouvé, le compilateur ne précédemment tient pas compte tout espace de noms des opérateurs de portée. S’il existe une meilleure correspondance dans la portée espace de noms, le compilateur actuel appelle correctement, alors que les compilateurs précédents ne le prendre en compte.  
  
 Cet avertissement doit être désactivé une fois que vous avez porté votre code vers la version actuelle.  Le compilateur peut fournir des faux positifs, génère cet avertissement pour le code où il n’existe aucun changement de comportement.  
  
 Cet avertissement est désactivé par défaut. Pour plus d’informations, consultez [avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L’exemple suivant génère l’erreur C4342 :  
  
```cpp  
// C4342.cpp  
// compile with: /EHsc /W1  
#include <fstream>  
#pragma warning(default: 4342)  
using namespace std;  
struct X : public ofstream {  
   X();  
};  
  
X::X() {  
   open( "ofs_bug_ev.txt." );  
   if ( is_open() ) {  
      *this << "Text" << "<-should be text" << endl;   // C4342  
      *this << ' ' << "<-should be space symbol" << endl;   // C4342  
   }  
}  
  
int main() {  
   X b;  
   b << "Text" << "<-should be text" << endl;  
   b << ' ' << "<-should be space symbol" << endl;  
}  
```
