---
title: "Avertissement du compilateur (niveau 3) C4534 | Microsoft Docs"
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
  - "c4534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4534"
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constructeur' ne peut pas être un constructeur par défaut pour la classe 'classe' en raison de l'argument par défaut  
  
 Une classe non managée peut avoir un constructeur avec des paramètres ayant les valeurs par défaut, le compilateur l'utilisera comme constructeur par défaut.  Une classe marquée avec le mot clé `value` n'utilisera pas un constructeur avec valeurs par défaut pour ces paramètres comme constructeur par défaut.  
  
 Pour plus d'informations, consultez [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C4534 :  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```