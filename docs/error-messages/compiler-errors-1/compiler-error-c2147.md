---
title: "Erreur du compilateur C2147 | Microsoft Docs"
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
  - "C2147"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2147"
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2147
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : 'identifier' est un nouveau mot clé  
  
 Vous avez utilisé un identificateur qui est désormais un mot clé réservé dans le langage.  
  
 L'exemple suivant génère l'erreur C2147 :  
  
```  
// C2147.cpp  
// compile with: /clr  
int main() {  
   int gcnew = 0;   // C2147  
   int i = 0;   // OK  
}  
```