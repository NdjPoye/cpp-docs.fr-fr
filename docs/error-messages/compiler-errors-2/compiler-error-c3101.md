---
title: "Erreur du compilateur C3101 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3101"
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Erreur du compilateur C3101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expression non conforme pour l'argument d'attribut nommé 'champ'  
  
 Lors de l'initialisation d'un argument d'attribut nommé, la valeur doit être une constante évaluée au moment de la compilation.  
  
 Pour plus d'informations sur les attributs, consultez [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3101 :  
  
```  
// C3101.cpp  
// compile with: /clr /c  
ref class AAttribute : System::Attribute {  
public:  
   int Field;  
};  
  
extern int i;  
  
[assembly:A(Field = i)];   // C3101  
[assembly:A(Field = 0)];   // OK  
```