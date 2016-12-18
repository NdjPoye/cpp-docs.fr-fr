---
title: "Erreur du compilateur C2472 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2472"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2472"
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2472
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' ne peut pas être généré dans le code managé : 'message' ; compilez avec \/clr pour générer une image mixte  
  
 Cette erreur se produit quand des types non pris en charge par le code managé sont utilisés dans un environnement CLR pur. Compilez avec **\/clr** pour résoudre l’erreur.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2472 :  
  
```  
// C2472.cpp // compile with: /clr:pure // C2472 expected #include <cstdlib> int main() { int * __ptr32 p32; int * __ptr64 p64; p32 = (int * __ptr32)malloc(4); p64 = p32; }  
```  
  
## Voir aussi  
 [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)