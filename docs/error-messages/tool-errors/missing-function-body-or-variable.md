---
title: Corps de fonction ou Variable manquant | Documents Microsoft
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
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
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
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: c80a5626e7f674ddca7d44e94aa8ab64c735c81e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/24/2017

---
# <a name="missing-function-body-or-variable"></a>Corps de fonction ou variable manquant
Avec seulement un prototype de fonction, le compilateur peut poursuivre sans erreur, mais l’éditeur de liens ne peut pas résoudre un appel à une adresse, car il n’existe aucun code de fonction ou un espace réservé pour la variable. Vous ne verrez pas cette erreur avant la création d’un appel à la fonction de l’éditeur de liens doit être résolue.  
  
## <a name="example"></a>Exemple  
 L’appel de fonction dans main entraîne l’erreur LNK2019, car le prototype permet au compilateur de considérer que la fonction existe.  L’éditeur de liens recherche que ce n’est pas.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## <a name="example"></a>Exemple  
 En C++, assurez-vous que vous incluez l’implémentation d’une fonction spécifique pour une classe et pas seulement un prototype dans la définition de classe. Si vous définissez la classe en dehors du fichier d’en-tête, veillez à inclure le nom de classe avant la fonction (`Classname::memberfunction`).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
