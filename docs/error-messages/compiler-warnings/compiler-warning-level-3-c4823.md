---
title: "Avertissement du compilateur (niveau 3) C4823 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4823"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4823"
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Avertissement du compilateur (niveau 3) C4823
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : utilise des pointeurs épingle mais les sémantiques de déroulement ne sont pas activées.Utilisez \/EHa  
  
 Pour désépingler un objet sur le saut managé désigné par un pointeur épingle déclaré dans une portée de bloc, le compilateur simule le comportement de destructeurs de classes locales, « prétendant » que le pointeur épingle possède un destructeur qui annule les effets du pointeur.  Pour activer un appel à un destructeur après une levée exception, vous devez activer le déroulement d'objet, ce que vous pouvez faire avec [\/EHsc](../../build/reference/eh-exception-handling-model.md).  
  
 Vous pouvez également désépingler manuellement l'objet et ignorer l'avertissement.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4823.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  
  
## Exemple  
 L'erreur C4823 peut également être générée à l'aide de **\/clr:oldSyntax**.  L'exemple suivant génère l'erreur C4823.  
  
```  
// C4823_b.cpp  
// compile with: /clr:oldSyntax /W3 /EHa-  
using namespace System;  
  
__gc struct G {  
   int m;  
};  
  
void f(G* pG) {  
   try {  
      int __pin* p = &pG->m;  
      // manually unpin, ignore warning  
      // p = 0;  
      throw new Exception;  
   }  
   catch(Exception*) {}  
}   // C4823  
  
int main() {  
   f( new G );  
}  
```