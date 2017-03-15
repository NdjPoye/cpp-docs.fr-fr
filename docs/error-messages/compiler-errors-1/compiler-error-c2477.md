---
title: "Erreur du compilateur C2477 | Microsoft Docs"
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
  - "C2477"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2477"
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2477
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : les données membres static ne peuvent pas être initialisées via une classe dérivée  
  
 Les données membres static d'une classe de modèle n'ont pas été initialisées correctement.  Ceci constitue un changement majeur par rapport aux versions du compilateur Visual C\+\+ antérieures à Visual Studio .NET 2003, afin de se conformer à la norme ISO C\+\+.  
  
 L'exemple suivant génère l'erreur C2477 :  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```