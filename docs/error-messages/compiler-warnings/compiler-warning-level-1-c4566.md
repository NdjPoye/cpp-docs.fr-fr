---
title: "Avertissement du compilateur (niveau 1) C4566 | Microsoft Docs"
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
  - "C4566"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4566"
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4566
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le caractère représenté par le nom de caractère universel 'car' ne peut pas être représenté dans la page de codes actuelle \(page\)  
  
 Tous les caractères Unicode ne peuvent pas être représentés dans votre page de codes ANSI actuelle.  
  
 Les chaînes étroites \(caractères à un octet\) sont converties en caractères multioctets alors que les chaînes étendues \(caractères à deux octets\) ne le sont pas.  
  
 L'exemple suivant génère l'erreur C4566 :  
  
```  
// C4566.cpp  
// compile with: /W1  
int main() {  
   char c1 = '\u03a0';   // C4566  
   char c2 = '\u0642';   // C4566  
  
   wchar_t c3 = L'\u03a0';   // OK  
   wchar_t c4 = L'\u0642';   // OK  
}  
```