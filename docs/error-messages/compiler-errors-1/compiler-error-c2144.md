---
title: "Erreur du compilateur C2144 | Microsoft Docs"
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
  - "C2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2144"
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : 'type' doit être précédé de 'jeton'  
  
 Le compilateur attendait `token` et a trouvé `type` à la place.  
  
 Cette erreur peut être provoquée par l'absence d'une accolade fermante, d'une parenthèse fermante ou d'un point\-virgule.  
  
 L'erreur C2144 peut également se produire lors d'une tentative de création d'une macro à partir d'un mot clé CLR qui contient un caractère d'espace blanc.  
  
 L'erreur C2144 peut également être générée si vous essayez d'effectuer un transfert de type.  Pour plus d'informations, consultez [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2144 :  
  
```  
// C2144.cpp  
// compile with: /clr /c  
#define REF ref  
REF struct MyStruct0;   // C2144  
  
// OK  
#define REF1 ref struct  
REF1 MyStruct1;  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C2144 :  
  
```  
// C2144_2.cpp  
// compile with: /clr /c  
ref struct X {  
  
   property double MultiDimProp[,,] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp[int , int, int] {  
      double get(int, int, int) { return 1; }  
      void set(int i, int j, int k, double l) {}  
   }  
  
   property double MultiDimProp2[] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp2[int] {  
      double get(int) { return 1; }  
      void set(int i, double l) {}  
   }  
};  
```