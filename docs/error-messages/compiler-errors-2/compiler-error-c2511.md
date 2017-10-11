---
title: Erreur du compilateur C2511 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1ba01f808fb4dd618291777c1da7490b3b95af3c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2511"></a>Erreur du compilateur C2511
'identificateur' : la fonction membre introuvable dans 'classe' surchargée  
  
 Aucune version de la fonction n’est déclarée avec les paramètres spécifiés.  Causes possibles :  
  
1.  Paramètres incorrects passés à la fonction.  
  
2.  Paramètres passés dans un ordre incorrect.  
  
3.  Orthographe incorrecte des noms de paramètre.  
  
 L’exemple suivant génère l’erreur C2511 :  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```
