---
title: "Erreur du compilateur C3352 | Microsoft Docs"
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
  - "C3352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3352"
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la fonction spécifiée est incompatible avec le type délégué 'type'  
  
 Les listes de paramètres de `function` et du délégué ne concordent pas.  
  
 Pour plus d'informations, consultez [délégué](../../windows/delegate-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3352 :  
  
```  
// C3352.cpp  
// compile with: /clr  
delegate int D( int, int );  
ref class C {  
public:  
   int mf( int ) {  
      return 1;  
   }  
  
   // Uncomment the following line to resolve.  
   // int mf(int, int) { return 1; }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352  
}  
```  
  
 L'exemple suivant génère l'erreur C3352 :  
  
```  
// C3352_2.cpp  
// compile with: /clr:oldSyntax  
__delegate int D(int, int);  
  
__gc class C {  
public:  
   int mf(int) {  
      return 1;  
   }  
  
   // Uncomment the following line to resolve.  
   // int mf(int, int) { return 1; }  
};  
  
int main() {  
   C *pC = new C;  
   System::Delegate *pD = new D(pC, &C::mf);   // C3352  
}  
```