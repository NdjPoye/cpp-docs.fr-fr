---
title: Compilateur avertissement (niveau 1) C4005 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf0c5777cecf89bb0723b30c87dc4c856de0a016
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4005"></a>Compilateur avertissement (niveau 1) C4005
'identificateur' : redéfinition de macro  
  
 Identificateur de la macro est défini à deux reprises. Le compilateur utilise la deuxième définition de macro.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Définition d’une macro sur la ligne de commande et dans le code avec un `#define` la directive.  
  
2.  Macros importées depuis des fichiers include.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Supprimez l’une des définitions.  
  
2.  Utilisez un [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) directive avant la seconde définition.  
  
 L’exemple suivant génère l’erreur C4005 :  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```