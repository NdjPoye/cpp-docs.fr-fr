---
title: "Erreur du compilateur C3821 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3821"
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Erreur du compilateur C3821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction : impossible d'utiliser un type ou une fonction managée dans une fonction non managée  
  
 Les fonctions avec un assembly inline ou [setjmp](../../c-runtime-library/reference/setjmp.md) ne peuvent pas contenir des types valeur ou des classes managées.  Pour remédier à cette erreur, supprimez l'assembly inline et `setjmp` ou supprimez les objets managés.  
  
 L'erreur C3821 peut également se produire si vous essayez d'utiliser le stockage automatique dans une fonction vararg.  Pour plus d’informations, consultez [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) et [Sémantique de pile C\+\+ pour les types de référence](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3821 :  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C3821 :  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C3821 :  
  
```  
// C3821c.cpp  
// compile with: /clr:oldSyntax  
// processor: /x86  
__gc  class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A *a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```