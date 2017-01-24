---
title: "Portabilit&#233; aux limites ABI (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Portabilit&#233; aux limites ABI (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez des types suffisamment portables et conventions aux limites de l'interface.  Un "type portable" est un type C intégré ou une structure qui contient uniquement des types C intégrés.  Les types de fichiers peuvent être utilisés lorsque l'appelant et l'appelé sont d'accord sur la mise en page, la convention d'appel, etc. C'est possible que si les deux arguments sont compilés avec les mêmes compilateur et paramètres de compilateur.  
  
## Comment aplatir une classe pour la portabilité C  
 Lorsque les appelants peuvent être compilés avec un autre compilateur de langage, puis « aplatis » vers une API « C externe » avec une convention d'appel spécifique :  
  
```cpp  
// class widget {  
//   widget();  
//   ~widget();  
//   double method( int, gadget& );  
// };  
extern “C” {    // functions using explicit “this”  
  struct widget;   // + opaque type (fwd decl only)  
  widget* STDCALL widget_create();    // ctor → create new  “this”  
  void STDCALL widget_destroy( widget* );    // dtor → consume “this”  
  double STDCALL widget_method( widget*, int, gadget* );    // method → use “this”  
}  
  
```  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)