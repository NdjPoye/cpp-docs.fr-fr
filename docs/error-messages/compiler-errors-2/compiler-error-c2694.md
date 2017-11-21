---
title: Erreur du compilateur C2694 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2694
dev_langs: C++
helpviewer_keywords: C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b81a6ee838a1d30928e8cebb8ef581c23644afcf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2694"></a>Erreur du compilateur C2694
'override' : fonction virtuelle de substitution a des spécifications d’exception moins restrictive que la classe de base 'base' de fonction membre virtuel  
  
 Une fonction virtuelle a été substituée, mais sous [/Za](../../build/reference/za-ze-disable-language-extensions.md), la fonction de substitution a moins restrictive [spécification d’exception](../../cpp/exception-specifications-throw-cpp.md).  
  
 L’exemple suivant génère l’erreur C2694 :  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```