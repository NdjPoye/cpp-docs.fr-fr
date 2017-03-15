---
title: "Erreur du compilateur C3893 | Microsoft Docs"
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
  - "C3893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3893"
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : l'utilisation comme l\-value des données membres initonly n'est autorisée que dans un constructeur d'instance de la classe 'nom\_type'  
  
 L'adresse des données membres [initonly](../../dotnet/initonly-cpp-cli.md) static ne peut être prise que dans un constructeur static.  
  
 L'adresse des données membres initonly d'instance \(non static\) ne peut être prise que dans des constructeurs d'instance \(non static\).  
  
 L'exemple suivant génère l'erreur C3893 :  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```