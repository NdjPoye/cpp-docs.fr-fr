---
title: "__super | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__super_cpp"
  - "__super"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__super (mot clé) (C++)"
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __super
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Permet de déclarer explicitement que vous appelez une implémentation de classe de base pour une fonction que vous substituez.  
  
## Syntaxe  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## Notes  
 Toutes les méthodes de classe de base accessibles sont considérées pendant la phase de résolution de surcharge, et la fonction qui fournit la meilleure correspondance est celle qui est appelée.  
  
 `__super` peut apparaître uniquement dans le corps d'une fonction membre.  
  
 `__super` ne peut pas être utilisé avec une déclaration using.  Pour plus d'informations, consultez [Déclaration using](../cpp/using-declaration.md).  
  
 Avec l'introduction des [attributs](../windows/cpp-attributes-reference.md) qui injectent du code, celui\-ci peut contenir une ou plusieurs classes de base dont vous pouvez ignorer les noms mais qui contiennent des méthodes que vous souhaitez appeler.  
  
## Exemple  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)