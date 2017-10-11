---
title: Compilateur avertissement (niveau 1) C4010 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b6a0c84d5138cf2ae8a7a6279d9dc0fde9fe9512
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4010"></a>Compilateur avertissement (niveau 1) C4010
commentaire sur une ligne contient le caractère de continuation de ligne  
  
 Un commentaire sur une ligne, commençant par / /, contient une barre oblique inverse (\\) qui sert d’un caractère de continuation de ligne. Le compilateur considère que la ligne suivante est une suite et le traite comme un commentaire.  
  
 Certains syntaxiques éditeurs n’indiquent pas la ligne qui suit le caractère de continuation en tant que commentaire. Ignorer les couleurs de syntaxe sur les lignes qui entraînent cet avertissement.  
  
 L’exemple suivant génère l’erreur C4010 :  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```
