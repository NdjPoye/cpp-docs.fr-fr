---
title: "Comment&#160;: it&#233;rer au sein d&#39;une collection d&#233;finie par l&#39;utilisateur en utilisant for each | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collections, itérer"
ms.assetid: 0efd9e3c-d7bb-4f6c-9938-e0e65d191433
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Comment&#160;: it&#233;rer au sein d&#39;une collection d&#233;finie par l&#39;utilisateur en utilisant for each
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour qu'une classe soit une collection managée, elle a besoin d'une fonction non\-privée de GetEnumerator qui retourne un handle à une classe d'énumérateur ou une interface.  Une classe d'énumérateur doit contenir la déclaration de la fonction statique de MoveNext et la propriété en cours.  
  
## Exemple  
 Collection simple définie par l'utilisateur avec les types référence.  
  
```  
// for_each_user_defined_collections.cpp  
// compile with: /clr  
using namespace System;  
public interface struct IMyEnumerator {  
   bool MoveNext();  
   property Object^ Current {  
      Object^ get();  
   }  
   void Reset();  
};  
  
public ref struct MyArray {     
  
   MyArray( array<int>^ d ) {  
      data = d;  
   }  
  
   ref struct enumerator : IMyEnumerator {  
      enumerator( MyArray^ myArr ) {  
         colInst = myArr;  
         currentIndex = -1;  
      }  
  
      virtual bool MoveNext() {  
         if( currentIndex < colInst->data->Length - 1 ) {  
            currentIndex++;  
            return true;  
         }  
         return false;  
      }  
  
      property Object^ Current {  
         virtual Object^ get() {  
            return colInst->data[currentIndex];  
         }  
      };  
  
      virtual void Reset() {}  
      ~enumerator() {}  
  
      MyArray^ colInst;  
      int currentIndex;  
   };  
  
   array<int>^ data;  
  
   IMyEnumerator^ GetEnumerator() {  
      return gcnew enumerator(this);  
   }  
};  
  
int main() {  
   int retval = 0;  
  
   MyArray^ col = gcnew MyArray( gcnew array<int>{10, 20, 30 } );  
  
   for each ( Object^ c in col )  
      retval += (int)c;  
  
   retval -= 10 + 20 + 30;  
  
   for each ( int c in gcnew MyArray( gcnew array<int>{10, 20, 30 } ) )  
      retval += c;  
  
   retval -= 10 + 20 + 30;  
  
   Console::WriteLine("Return Code: {0}", retval );  
   return retval;  
}  
```  
  
  **Code de Retour : 0**   
## Voir aussi  
 [for each, in](../dotnet/for-each-in.md)