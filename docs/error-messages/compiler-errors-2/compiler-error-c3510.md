---
title: Erreur du compilateur C3510 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9603a4f94106d491ea5e14f30b36b1b230554ad2
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3510"></a>Erreur du compilateur C3510
ne peut pas localiser de bibliothèque de types dépendante 'type_lib'  
  
 [no_registry](../../preprocessor/no-registry.md) et [auto_search](../../preprocessor/auto-search.md) ont été passés à `#import` , mais le compilateur n’a pas pu trouver une bibliothèque de types référencée.  
  
 Pour résoudre cette erreur, assurez-vous que toutes les bibliothèques de types et des bibliothèques de types référencées sont disponibles pour le compilateur.  
  
 L’exemple suivant génère l’erreur C3510 :  
  
 Supposons que les bibliothèques de deux types suivantes ont été créées et que C3510a.tlb a été supprimé ou non sur le chemin d’accès.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 Et ensuite le code source pour la deuxième bibliothèque de types :  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 Et le code client :  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```
