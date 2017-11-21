---
title: Compilateur avertissement (niveau 1) C4020 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4020
dev_langs: C++
helpviewer_keywords: C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4980961746f2711fcf0655dd37b5f37d8d8124e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4020"></a>Compilateur avertissement (niveau 1) C4020
'fonction' : paramètres réels trop nombreux  
  
 Le nombre de paramètres réels dans un appel de fonction dépasse le nombre de paramètres formels dans la définition ou le prototype de fonction. Le compilateur passe les paramètres réels supplémentaires en fonction de la convention d’appel de la fonction.  
  
 L’exemple suivant génère l’erreur C4020 :  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 Résolution possible :  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```