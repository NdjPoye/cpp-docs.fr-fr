---
title: "Erreur du compilateur C3904 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3904"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3904"
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C3904
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'accesseur\_propriété' : doit spécifier 'nombre' paramètre\(s\)  
  
 Vérifiez le nombre de paramètres dans vos méthodes `get` et `set` par rapport aux dimensions de la propriété.  
  
-   Le nombre de paramètres de la méthode `get` doit être égal au nombre de dimensions de la propriété ou être nul pour les propriétés non indexées.  
  
-   Le nombre de paramètres de la méthode `set` doit être supérieur de un au nombre de dimensions de la propriété.  
  
 Pour plus d'informations, consultez [property](../../windows/property-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3904 :  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C3904 :  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```