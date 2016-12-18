---
title: "Erreur du compilateur C3894 | Microsoft Docs"
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
  - "C3894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3894"
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : l'utilisation comme l\-value des données membre static initonly n'est autorisée que dans le constructeur de classe de la classe 'classe'  
  
 Les données membres static [initonly](../../dotnet/initonly-cpp-cli.md) ne peuvent être utilisées comme l\-value qu'à leur point de déclaration ou dans un constructeur static.  
  
 Les données membres initonly de l'instance \(non static\) ne peuvent être utilisées comme l\-value qu'à leur point de déclaration ou dans des constructeurs d'instance \(non static\).  
  
 L'exemple suivant génère l'erreur C3894 :  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```