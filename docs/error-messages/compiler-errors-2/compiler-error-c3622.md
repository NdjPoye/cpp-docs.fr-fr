---
title: "Erreur du compilateur C3622 | Microsoft Docs"
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
  - "C3622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3622"
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : une classe déclarée comme 'MotClé' ne peut pas être instanciée  
  
 Vous avez essayé d'instancier une classe marquée [abstract](../../windows/abstract-cpp-component-extensions.md) \(ou [\_\_abstract](../../misc/abstract.md)\).  Une classe marquée abstract peut être une classe de base, mais elle ne peut pas être instanciée.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3622 :  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C3622 :  
  
```  
// C3622_b.cpp  
// compile with: /clr:oldSyntax  
__abstract class a {  
};  
int main() {  
   a aa;   // C3622  
}  
```