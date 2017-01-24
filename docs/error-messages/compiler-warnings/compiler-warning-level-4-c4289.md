---
title: "Avertissement du compilateur (niveau 4) C4289 | Microsoft Docs"
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
  - "C4289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4289"
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : 'var' : variable de contrôle de boucle déclarée dans la boucle for utilisée à l'extérieur de la portée de la boucle  
  
 Lors de la compilation avec [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) et **\/Zc:forScope\-**, une variable déclarée dans une boucle [for](../../cpp/for-statement-cpp.md) a été utilisée après la portée de la boucle **for**.  
  
 Consultez [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) pour obtenir des informations sur la spécification du comportement standard des boucles **for** avec **\/Ze**.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4289 :  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```