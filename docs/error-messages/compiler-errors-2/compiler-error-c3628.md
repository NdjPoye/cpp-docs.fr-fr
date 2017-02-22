---
title: "Erreur du compilateur C3628 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3628"
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe de base' : les classes managées ou WinRT ne prennent en charge que les héritages publics  
  
 Une tentative a été effectuée pour utiliser une classe managée ou WinRT en tant que classe de base [privée](../../cpp/private-cpp.md) ou [protégée](../../cpp/protected-cpp.md).  Une classe managée ou WinRT peut uniquement être utilisée en tant que classe de base avec accès [public](../../cpp/public-cpp.md).  
  
 L'exemple suivant génère l'erreur C3628 et montre comment la corriger :  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
  
 L'exemple suivant génère l'erreur C3628 et montre comment la corriger :  
  
```  
// C3628b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class B {  
};  
  
__gc class D : B {   // C3628, private is the default access level  
  
// The following line resolves the error.  
// __gc class D : public B {  
};  
  
int main() {  
}  
```