---
title: "Erreur du compilateur C2879 | Microsoft Docs"
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
  - "C2879"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2879"
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2879
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : seul un espace de noms existant peut être renommé par une définition d'alias d'espace de noms  
  
 Vous ne pouvez pas créer un [alias d'espace de noms](../../misc/namespace-alias.md) vers un symbole autre qu'un espace de noms.  
  
 L'exemple suivant génère l'erreur C2879 :  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```