---
title: "Avertissement du compilateur (niveau 1) C4964 | Microsoft Docs"
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
  - "C4964"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4964"
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4964
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aucune option d'optimisation n'a été spécifiée ; les informations de profil ne seront pas recueillies  
  
 Les options [\/GL](../../build/reference/gl-whole-program-optimization.md) et [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) ont été spécifiées, mais aucune optimisation n'a été demandée ; aucun fichier .pgc ne sera donc généré et, par conséquent, aucune optimisation guidée par profil ne sera possible.  
  
 Si vous souhaitez que des fichiers .pgc soient générés lors de l'exécution de votre application, spécifiez l'une des options du compilateur [\/O](../../build/reference/o-options-optimize-code.md).  
  
 L'exemple suivant génère l'erreur C4964 :  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```