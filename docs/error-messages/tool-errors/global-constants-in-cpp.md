---
title: Constantes globales en C++ | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 766e1a6f48ecf3f64110e64d916c50d92c89345d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="global-constants-in-c"></a>Constantes globales en C++
Constantes globales en C++ ont une liaison static. Cela est différent de celui de C. Si vous essayez d’utiliser un global constante en C++ dans plusieurs fichiers vous obtenez une erreur externe non résolue. Le compilateur optimise les constantes globales, en laissant aucun espace réservé pour la variable.  
  
 Pour résoudre cette erreur consiste à inclure les initialisations dans un fichier d’en-tête et inclure cet en-tête dans vos fichiers CPP lorsque cela est nécessaire, comme s’il s’agissait de prototype de fonction. Une autre possibilité consiste à rendre la variable non constante et utiliser une référence constante lors de l’évaluation d’elle.  
  
 L’exemple suivant génère l’erreur C2019 :  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 Puis,  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)