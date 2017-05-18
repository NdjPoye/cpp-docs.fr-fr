---
title: Erreur du compilateur C3836 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 0708b8c9bf59e1c2ea3751fbb91192d6b873d8ec
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3836"></a>Erreur du compilateur C3836
constructeur statique n’est pas autorisé à avoir une liste d’initialiseurs de membres  
  
 Une classe managée ne peut pas avoir un constructeur statique qui possède également une liste d’initialisation de membre. Constructeurs de classe statique sont appelées par le common language runtime pour l’initialisation, l’initialisation des membres de données statiques de classe.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3836 :  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  

