---
title: "Erreur du compilateur C2705 | Microsoft Docs"
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
  - "C2705"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2705"
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2705
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'étiquette' : saut dans la portée 'bloc de gestion d'exceptions' non conforme  
  
 L'exécution passe à une étiquette dans un bloc `try`\/`catch`, `__try`\/`__except`, `__try`\/`__finally`.  Pour plus d'informations, consultez [Exception Handling](../../cpp/exception-handling-in-visual-cpp.md).  
  
 L'exemple suivant génère l'erreur C2705 :  
  
```  
// C2705.cpp  
int main() {  
goto trouble;  
   __try {  
      trouble: ;   // C2705  
   }  
   __finally {}  
  
   // try the following line instead  
   // trouble: ;  
}  
```