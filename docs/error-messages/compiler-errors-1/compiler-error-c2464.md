---
title: "Erreur du compilateur C2464 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2464"
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2464
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : impossible d'utiliser 'new' pour allouer une référence  
  
 Un identificateur de référence a été alloué à l'aide de l'opérateur `new`.  Les références n'étant pas des objets en mémoire, `new` ne peut pas retourner un pointeur vers elles.  Pour déclarer une référence, utilisez la syntaxe de déclaration de variable standard.  
  
 L'exemple suivant génère l'erreur C2464 :  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```