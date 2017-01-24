---
title: "Avertissement du compilateur (niveau 1) C4930 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4930"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4930"
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4930
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'prototype' : fonction prototypée non appelée \(était\-ce la définition de variable souhaitée ?\)  
  
 Le compilateur a détecté un prototype de fonction non utilisé.  Si le prototype était destiné à faire office de déclaration de variable, supprimez les parenthèses.  
  
 L'exemple suivant génère l'erreur C4930 :  
  
```  
// C4930.cpp  
// compile with: /W1  
class Lock {  
public:  
   int i;  
};  
  
void f() {  
   Lock theLock();   // C4930  
   // try the following line instead  
   // Lock theLock;  
}  
  
int main() {  
}  
```  
  
 C4930 peut également se produire lorsque le compilateur ne peut pas distinguer entre une déclaration de prototype de fonction et un appel de fonction.  
  
 L'exemple suivant génère l'erreur C4930 :  
  
```  
// C4930b.cpp  
// compile with: /EHsc /W1  
  
class BooleanException  
{  
   bool _result;  
  
public:  
   BooleanException(bool result)  
      : _result(result)  
   {  
   }  
  
   bool GetResult() const  
   {  
      return _result;  
   }  
};  
  
template<class T = BooleanException>  
class IfFailedThrow  
{  
public:  
   IfFailedThrow(bool result)  
   {  
      if (!result)  
      {  
         throw T(result);  
      }  
   }  
};  
  
class MyClass  
{  
public:  
   bool MyFunc()  
   {  
      try  
      {  
         IfFailedThrow<>(MyMethod()); // C4930  
  
         // try one of the following lines instead  
         // IfFailedThrow<> ift(MyMethod());  
         // IfFailedThrow<>(this->MyMethod());  
         // IfFailedThrow<>((*this).MyMethod());  
  
         return true;  
      }  
      catch (BooleanException e)  
      {  
         return e.GetResult();  
      }  
   }  
  
private:  
   bool MyMethod()  
   {  
      return true;  
   }  
};  
  
int main()  
{  
   MyClass myClass;  
   myClass.MyFunc();  
}  
```  
  
 Dans l'exemple ci\-dessus, le résultat d'une méthode qui n'accepte pas d'arguments est passé comme argument au constructeur d'une variable de classe locale sans nom.  L'ambiguïté de l'appel peut être levée en nommant la variable locale ou en préfixant l'appel de la méthode avec une instance d'objet et avec l'opérateur pointeur vers membre.