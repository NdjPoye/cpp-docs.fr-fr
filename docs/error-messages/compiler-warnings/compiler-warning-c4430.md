---
title: "Avertissement du compilateur C4430 | Microsoft Docs"
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
  - "C4430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4430"
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

spécificateur de type manquant \- int est pris en compte par défaut.Remarque : C ne prend plus en charge int par défaut  
  
 Cette erreur peut être due à la mise en conformité du compilateur pour Visual C\+\+ 2005 : toutes les déclarations doivent spécifier explicitement le type ; int n'est plus pris en compte par défaut.  
  
 C4430 est toujours émis en tant qu'erreur.  Vous pouvez désactiver cet avertissement avec `#pragma warning` ou **\/wd** ; consultez [warning](../../preprocessor/warning.md) ou [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../../build/reference/compiler-option-warning-level.md) pour plus d'informations.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4430 :  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```