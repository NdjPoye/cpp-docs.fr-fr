---
title: "Erreur du compilateur C3142 | Microsoft Docs"
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
  - "C3142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3142"
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom\_propriété' : vous ne pouvez pas prendre l'adresse d'une propriété  
  
 L'adresse d'une propriété n'est pas accessible au développeur.  
  
 L'exemple suivant génère l'erreur C3142 :  
  
```  
// C3142_2.cpp  
// compile with: /clr  
using namespace System;  
ref class CSize {  
private:  
   property int Size {  
      int get();  
   }  
};  
  
int main() {  
    &CSize::Size; // C3142  
}  
```  
  
 L'exemple suivant génère l'erreur C3142 :  
  
```  
// C3142.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc class CSize  
{  
   __property int get_Size();  
};  
  
int main()  
{  
   &CSize::Size;   // C3142  
}  
```