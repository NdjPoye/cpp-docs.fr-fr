---
title: Erreur du compilateur C3894 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3894
dev_langs:
- C++
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 46dffabb57e871e1635738434e7efb4812850379
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3894"></a>Erreur du compilateur C3894
'var' : utilisation comme l-value des données membres static initonly est autorisée uniquement dans le constructeur de classe de la classe 'classe'  
  
 Statique [initonly](../../dotnet/initonly-cpp-cli.md) données membres peuvent uniquement être utilisés comme l-values à leur point de déclaration ou dans un constructeur statique.  
  
 Instance (non statique) les données membres initonly peuvent uniquement être utilisés comme l-values à leur point de déclaration ou dans les constructeurs d’instance (non statique).  
  
 L’exemple suivant génère l’erreur C3894 :  
  
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
