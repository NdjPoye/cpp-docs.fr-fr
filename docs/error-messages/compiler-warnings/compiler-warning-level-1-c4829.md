---
title: "Avertissement du compilateur (niveau 1) C4829 | Microsoft Docs"
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
  - "C4829"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4829"
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4829
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Paramètres potentiellement incorrects de la fonction main.Considérez 'int main\(Platform::Array\<Platform::String^\>^ argv\)'  
  
 Certaines fonctions, telles que main, ne peuvent pas prendre de paramètres de type référence.  La compilation réussira, mais l'image résultante ne fonctionnera probablement pas.  
  
 L'exemple suivant génère l'erreur C4829 :  
  
```  
// C4829.cpp  
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp  
int main(Platform::String ^ s) {}   // C4829  
  
```