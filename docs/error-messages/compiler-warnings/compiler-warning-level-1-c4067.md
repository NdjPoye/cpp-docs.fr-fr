---
title: "Avertissement du compilateur (niveau 1) C4067 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4067"
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jetons inattendus après la directive du préprocesseur \- saut de ligne attendu  
  
 Le compilateur a trouvé et ignoré des caractères supplémentaires après une directive du préprocesseur.  Cet avertissement n'apparaît que sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
```  
// C4067a.cpp  
// compile with: /DX /Za /W1  
#pragma warning(default:4067)  
#if defined(X)  
#else  
#endif v   // C4067  
int main()  
{  
}  
```  
  
### Pour résoudre cet avertissement, essayez les opérations suivantes :  
  
1.  Compilez avec **\/Ze**.  
  
2.  Utilisez des délimiteurs de commentaires :  
  
```  
// C4067b.cpp  
// compile with: /DX /Za /W1  
#if defined(X)  
#else  
#endif  
int main()  
{  
}  
```