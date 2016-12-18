---
title: "Erreur du compilateur C3900 | Microsoft Docs"
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
  - "C3900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3900"
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : non autorisé dans la portée actuelle  
  
 Les blocs de propriété ne peuvent contenir que des déclarations de fonction et des définitions de fonction inline.  Aucun membre autre que des fonctions n'est autorisé dans les blocs de propriété.  Aucun typedef, aucun opérateur ou aucune fonction friend ne sont autorisés.  Pour plus d'informations, consultez [property](../../windows/property-cpp-component-extensions.md).  
  
 Les définitions d'événement ne peuvent contenir que des méthodes et fonctions d'accès.  
  
 L'exemple suivant génère l'erreur C3900 :  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 L'exemple suivant génère l'erreur C3900 :  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```