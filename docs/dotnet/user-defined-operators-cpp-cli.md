---
title: "Op&#233;rateurs d&#233;finis par l&#39;utilisateur (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateurs définis par l'utilisateur sous /clr"
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs d&#233;finis par l&#39;utilisateur (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs définis par l'utilisateur pour les types managés sont autorisés en tant que membres statiques ou membres d'instance, ou au niveau de l'étendue globale.  Toutefois, seuls les opérateurs statiques sont accessibles via les métadonnées à des clients écrits dans un langage autre que Visual C\+\+.  
  
 Dans un type de référence, l'un des paramètres d'un opérateur défini par l'utilisateur statique doit être l'un des suivants :  
  
-   Un descripteur \(`type` ^\) à une instance du type englobant.  
  
-   Une indirection de type référence \(`type`^& ou type^%\) à un handle à une instance du type englobant.  
  
 Dans un type de valeur, l'un des paramètres d'un opérateur défini par l'utilisateur statique doit être l'un des suivants :  
  
-   Du même type que le type sous\-jacent.  
  
-   Une indirection de type pointeur \(`type`^\) au type englobant.  
  
-   Une indirection de type référence \(`type`% ou `type`&\) au type englobant.  
  
-   Une indirection de type référence \(`type`^% ou `type`^&\) au descripteur.  
  
 Vous pouvez définir des opérateurs suivants :  
  
|Opérateur|Forme unaire ou binaire ?|  
|---------------|-------------------------------|  
|\!|Unaire|  
|\!\=|Binaire|  
|%|Binaire|  
|&|Unaire et binaire|  
|&&|Binaire|  
|\*|Unaire et binaire|  
|\+|Unaire et binaire|  
|\+\+|Unaire|  
|,|Binaire|  
|\-|Unaire et binaire|  
|\-\-|Unaire|  
|\-\>|Unaire|  
|\/|Binaire|  
|\<|Binaire|  
|\<\<|Binaire|  
|\<\=|Binaire|  
|\=|Binaire|  
|\=\=|Binaire|  
|\>|Binaire|  
|\>\=|Binaire|  
|\>\>|Binaire|  
|^|Binaire|  
|false|Unaire|  
|true|Unaire|  
|&#124;|Binaire|  
|&#124;&#124;|Binaire|  
|~|Unaire|  
  
## Exemple  
  
```  
// mcppv2_user-defined_operators.cpp  
// compile with: /clr  
using namespace System;  
public ref struct X {  
   X(int i) : m_i(i) {}  
   X() {}  
  
   int m_i;  
  
   // static, binary, user-defined operator  
   static X ^ operator + (X^ me, int i) {  
      return (gcnew X(me -> m_i + i));  
   }  
  
   // instance, binary, user-defined operator  
   X^ operator -( int i ) {  
      return gcnew X(this->m_i - i);  
   }  
  
   // instance, unary, user-defined pre-increment operator  
   X^ operator ++() {  
      return gcnew X(this->m_i++);  
   }  
  
   // instance, unary, user-defined post-increment operator  
   X^ operator ++(int i) {  
      return gcnew X(this->m_i++);  
   }  
  
   // static, unary user-defined pre- and post-increment operator  
   static X^ operator-- (X^ me) {  
      return (gcnew X(me -> m_i - 1));  
   }  
};  
  
int main() {  
   X ^hX = gcnew X(-5);  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX + 1;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX - (-1);  
   System::Console::WriteLine(hX -> m_i);  
  
   ++hX;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX++;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX--;  
   System::Console::WriteLine(hX -> m_i);  
  
   --hX;  
   System::Console::WriteLine(hX -> m_i);  
}  
```  
  
  **\-5**  
**\-4**  
**\-3**  
**\-2**  
**\-1**  
**\-2**  
**\-3**   
## Exemple  
 L'exemple suivant illustre la synthèse des opérateurs, qui est disponible uniquement lorsque vous utilisez **\/clr** pour compiler.  La synthèse d'opérateur crée la forme d'assignation d'un opérateur binaire, s'il n'est pas défini, où la partie gauche de l'opérateur d'affectation a un type CLR.  
  
```  
// mcppv2_user-defined_operators_2.cpp  
// compile with: /clr  
ref struct A {  
   A(int n) : m_n(n) {};  
   static A^ operator + (A^ r1, A^ r2) {  
      return gcnew A( r1->m_n + r2->m_n);  
   };  
   int m_n;  
};  
  
int main() {  
   A^ a1 = gcnew A(10);  
   A^ a2 = gcnew A(20);  
  
   a1 += a2;   // a1 = a1 + a2   += not defined in source  
   System::Console::WriteLine(a1->m_n);  
}  
```  
  
  **30**   
## Voir aussi  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)