---
title: "Erreur du compilateur C2728 | Microsoft Docs"
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
  - "C2728"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2728"
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2728
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : un tableau natif ne peut pas contenir ce type  
  
 La syntaxe de création de tableau a été utilisée pour créer un tableau d'objets managés ou WinRT.  Vous ne pouvez pas créer un tableau d'objets managés ou WinRT à l'aide de la syntaxe du tableau natif.  
  
 Pour plus d'informations, consultez [tableau](../../windows/arrays-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C2728 et montre comment la corriger :  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  
  
 Un tableau [\_nogc](../../misc/nogc.md) ne peut pas être d'un type [\_\_gc](../../misc/gc.md).  
  
 L'exemple suivant génère l'erreur C2728 et montre comment la corriger :  
  
```  
// C2728_b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
int main() {  
   int __gc* arr __nogc[5];   // C2728  
  
   // try the following line instead  
   int arr2 __gc[];  
}  
```