---
title: "Avertissement du compilateur (niveau 4) C4001 | Microsoft Docs"
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
  - "C4001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4001"
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard 'single line comment' utilisée  
  
 Les commentaires sur une seule ligne sont standard en C\+\+ et non standard en C.  En mode de compatibilité ANSI stricte \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\), les fichiers C qui contiennent des commentaires sur une seule ligne génèrent l'avertissement C4001 en raison de l'utilisation d'une extension non standard.  Les commentaires sur une seule ligne sont standard en C\+\+, les fichiers C contenant ces commentaires ne génèrent donc pas C4001 lors de la compilation avec les extensions Microsoft \(\/Ze\).  
  
## Exemple  
 Pour éliminer l'avertissement, supprimez les marques de commentaire [\#pragma warning\(disable:4001\)](../../preprocessor/warning.md).  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```