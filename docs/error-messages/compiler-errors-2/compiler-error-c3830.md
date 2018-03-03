---
title: Erreur du compilateur C3830 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3830
dev_langs:
- C++
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 692a2480a161a97595d3e1b2212bbddb008b7efb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3830"></a>Erreur du compilateur C3830
'type1' : ne peut pas hériter de 'type2', les types valeur peuvent uniquement hériter des classes d’interface  
  
 Un type valeur ne peut pas hériter d’une classe de base.  Pour plus d’informations, consultez [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3830 :  
  
```  
// C3830a.cpp  
// compile with: /clr /c  
public value struct MyStruct4 {  
   int i;  
};  
  
public value class MyClass : public MyStruct4 {};   // C3830  
  
// OK  
public interface struct MyInterface4 {  
   void i();  
};  
  
public value class MyClass2 : public MyInterface4 {  
public:  
   virtual void i(){}  
};  
```  
