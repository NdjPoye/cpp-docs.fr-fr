---
title: "Erreur du compilateur C2346 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2346"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2346"
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Erreur du compilateur C2346
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' ne peut pas être compilé comme code natif : raison  
  
 Le compilateur n'a pas pu compiler une fonction en code MSIL.  
  
 Pour plus d’informations, consultez [managé, non managé](../../preprocessor/managed-unmanaged.md) et [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### Pour corriger cette erreur  
  
1.  Dans la fonction, supprimez le code qui ne peut pas être compilé en code MSIL.  
  
2.  Ne compilez pas le module avec **\/clr**, ni ne marquez la fonction comme non managé avec le pragma non managé.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2346 :  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```