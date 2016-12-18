---
title: "Avertissement du compilateur (niveau 1) C4288 | Microsoft Docs"
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
  - "C4288"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4288"
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4288
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : 'var' : variable de contrôle de boucle déclarée dans la boucle for utilisée à l'extérieur de la portée de la boucle ; conflit avec la déclaration de la portée externe  
  
 Lors de la compilation avec [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) et **\/Zc:forscope\-**, une variable déclarée dans une boucle **for** a été utilisée après la portée de la boucle [for](../../cpp/for-statement-cpp.md).  Une extension Microsoft du langage C\+\+ permet à cette variable de rester dans la portée, C4288 vous rappelle que la première déclaration de la variable n'est pas utilisée.  
  
 Consultez [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) pour obtenir des informations sur la spécification de l'extension Microsoft des boucles **for** avec \/Ze.  
  
 L'exemple suivant génère l'erreur C4288 :  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```