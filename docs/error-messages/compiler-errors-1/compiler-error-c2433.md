---
title: "Erreur du compilateur C2433 | Microsoft Docs"
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
  - "C2433"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2433"
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2433
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : 'modificateur' non autorisé sur les déclarations de données  
  
 Les modificateurs `friend`, `virtual` et `inline` ne peuvent être utilisés pour les déclarations de données.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2433 :  
  
```  
// C2433.cpp  
class C{};  
  
int main() {  
   inline C c;   // C2433  
}  
```