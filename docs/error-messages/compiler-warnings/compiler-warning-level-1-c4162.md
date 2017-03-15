---
title: "Avertissement du compilateur (niveau 1) C4162 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4162"
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : aucune fonction avec liaison C n'a été trouvée  
  
 Une fonction avec liaison C est déclarée mais introuvable.  
  
 Pour résoudre cet avertissement, compilez dans un fichier .c \(appelez le compilateur C\).  Si vous devez appeler le compilateur C\+\+, placez extern "C" avant la déclaration de fonction.  
  
 L'exemple suivant génère l'erreur C4162 :  
  
```  
// C4162.cpp  
// compile with: /c /W1  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)   // C4162  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```  
  
 Résolution possible :  
  
```  
// C4162b.cpp  
// compile with: /c  
extern "C"  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```