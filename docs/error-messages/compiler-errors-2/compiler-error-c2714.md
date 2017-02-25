---
title: "Erreur du compilateur C2714 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2714"
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_alignof\(void\) n'est pas autorisé  
  
 Une valeur non valide a été passée à un opérateur.  
  
 Pour plus d'informations, consultez [\_\_alignof, opérateur](../../cpp/alignof-operator.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2714 :  
  
```  
// C2714.cpp  
int main() {  
   return __alignof(void);   // C2714  
   return __alignof(char);   // OK  
}  
```