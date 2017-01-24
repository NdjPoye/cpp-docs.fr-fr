---
title: "Avertissement du compilateur (niveau 1) C4258 | Microsoft Docs"
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
  - "C4258"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4258"
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4258
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : définition provenant de la boucle for ignorée ; la définition provenant de la portée englobante est utilisée  
  
 Sous [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) et [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md), les variables définies dans une boucle [for](../../cpp/for-statement-cpp.md) sortent de la portée après la fin de la boucle **for**.  Cet avertissement survient si une variable de même nom que la variable de boucle, mais définie dans la boucle englobante, est réutilisée dans la portée contenant la boucle **for**.  Par exemple :  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```