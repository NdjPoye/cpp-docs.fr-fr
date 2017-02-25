---
title: "Erreur du compilateur C3828 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3828"
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C3828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type objet' : arguments de positionnement non autorisés lors de la création d'instances de classes managées ou WinRT  
  
 Lorsque vous créez un objet d'un type managé ou Windows Runtime, vous ne pouvez pas utiliser la forme positionnement de l'opérateur [ref new, gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) ou [new](../../cpp/new-operator-cpp.md).  
  
 L'exemple suivant génère l'erreur C3828 et montre comment la corriger :  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```