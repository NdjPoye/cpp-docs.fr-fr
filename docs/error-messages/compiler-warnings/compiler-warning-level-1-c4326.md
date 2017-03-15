---
title: "Avertissement du compilateur (niveau 1) C4326 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4326"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4326"
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4326
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le type de retour de 'fonction' doit être 'type1' au lieu de 'type2'  
  
 Une fonction a retourné un type autre que ***type1***.  Par exemple, en utilisant [\/Za](../../build/reference/za-ze-disable-language-extensions.md), main n'a pas retourné un `int`.  
  
 L'exemple suivant génère l'erreur C4326 :  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```