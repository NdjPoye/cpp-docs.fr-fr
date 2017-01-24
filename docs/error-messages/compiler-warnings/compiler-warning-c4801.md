---
title: "Avertissement du compilateur C4801 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4801"
ms.assetid: 05b29dff-15ef-42ca-9712-dc993afc4fd6
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le retour par référence n'est pas vérifiable : raison  
  
 Vous ne pouvez pas stocker de référence de suivi dans une variable locale, puis la retourner de façon vérifiable.  
  
 Une référence ne peut être retournée de façon vérifiable que si elle peut être suivie par le vérificateur depuis sa création jusqu'au point de retour et s'il s'agit d'une référence à un élément d'un tableau ou d'un membre d'une classe.  
  
 Pour plus d'informations, consultez [Peverify.exe \(PEVerify Tool\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md).  
  
 Pour être vérifiable, une référence doit rester sur la pile depuis sa création jusqu'au point de retour.  
  
 C4801 est toujours émis en tant qu'erreur.  Vous pouvez désactiver cet avertissement avec `#pragma warning` ou **\/wd** ; consultez [warning](../../preprocessor/warning.md) ou [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../../build/reference/compiler-option-warning-level.md) pour plus d'informations.  
  
## Exemple  
 L'erreur C4801 est générée si le vérificateur ne peut pas consulter l'adresse spécifiée ; il doit donc supposer qu'il peut s'agir déréférence non vérifiable.  L'exemple suivant génère l'erreur C4801 :  
  
```  
// C4801.cpp  
// compile with: /clr:safe /c  
int% f(int% p) {  
   return p;   // C4801  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4801 :  
  
```  
// C4801_b.cpp  
// compile with: /clr:safe /c  
  
int% f(int i, array<int>^ ar) {  
   int x;  
   int% bri = x;   // cannot return a byref to a local.  
   if (i < ar->Length) {  
      bri = ar[i];   // this byref is ok.  
   }  
  
   return bri;   // C4801 not returned within the basic block  
}  
```  
  
## Exemple  
 L'erreur C4801 peut également se produire si vous essayez de déréférencer et de retourner une valeur de référence dans un bloc try.  Cela empêchera toute vérification du code, car la pile est effacée à la fin d'un bloc try, ce qui détruit toute valeur de retour sur la pile.  Déréférencez plutôt le type référence et assignez\-le à une variable pour garantir qu'aucune exception ne sera levée.  Ensuite, à la fin de la fonction, déréférencez à nouveau le type référence et retournez\-le.  
  
 L'exemple suivant génère l'erreur C4801 :  
  
```  
// C4801_c.cpp  
// compile with: /clr:safe  
using namespace System;  
  
ref class StackEmptyException : public System::Exception {};  
ref class StackFullException : public System::Exception {};  
  
template <typename T>  
ref struct Stack {  
  
   Stack() {  
      topElem = -1;   // initialize stack  
      stackPtr = gcnew array<T>(10);  
   }  
  
   void push(const T%);  
   T% top();  
  
private:  
   int topElem;    
   array<T>^ stackPtr;    
};  
  
template <typename T>   
T% Stack<T>::top() {  
   try {  
      return stackPtr[topElem];   // C4801  
      // Try the following line instead.  
      // T% deadstore = stackPtr[topElem] ;  
   }  
  
   catch (System::IndexOutOfRangeException ^ e) {  
      throw gcnew StackEmptyException();  
   }  
  
   catch (System::Exception ^ e) {  
      throw;  
   }  
  
   return stackPtr[topElem] ;  
}  
  
int main() {  
   typedef Stack<Int32> IntStack;  
   IntStack ^ is = gcnew IntStack();  
  
   int i = 1;  
   while (1) {  
      try {  
         is->push(i++);  
      }  
      catch (System::Exception ^ e) {  
         break;  
      }  
      Console::Write("{0} ", is->top());  
   }  
}  
```