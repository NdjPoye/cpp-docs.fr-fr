---
title: "Erreur du compilateur C2899 | Microsoft Docs"
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
  - "C2899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2899"
ms.assetid: a8942605-5bef-4d1c-b74a-41ae25423b22
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

typename ne peut pas être utilisé à l'extérieur d'une déclaration de modèle  
  
 Le mot clé [typename](../../cpp/typename.md) ne peut être utilisé que dans la définition ou la déclaration d'un modèle.  Il peut être utilisé de deux manières dans la déclaration d'un modèle :  
  
```  
// C2899.cpp  
// compile with: /c  
template<typename T>   
class X {};  
  
// Another way  
template<class T>   
struct XX {  
   typename T::A a;   // T::A is a type  
};  
```  
  
 L'exemple suivant génère l'erreur C2899 :  
  
```  
// C2899b.cpp  
// compile with: /c  
struct Y {  
   typedef int B;  
   typename Y::B b;   // C2899  
};  
  
```