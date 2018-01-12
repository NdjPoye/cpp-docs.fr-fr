---
title: Compilateur avertissement (niveau 1) C4584 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4584
dev_langs: C++
helpviewer_keywords: C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba427de26d07851c5bf2a2dd3f599c4cbe7afc5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4584"></a>Avertissement du compilateur (niveau 1) C4584
'classe1' : classe de base 'classe2' est déjà une classe de base de 'class3'  
  
 La classe définie hérite de deux classes, qui hérite de l’autre. Exemple :  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 Dans ce cas, un avertissement est émis sur la classe C, car il hérite de la classe A et de la classe B, laquelle hérite également de la classe A. Cet avertissement est un rappel que vous devez qualifier complètement l’utilisation des membres de ces classes de base ou une erreur du compilateur est générée en raison de l’ambiguïté quant au membre de classe auquel vous faites référence.