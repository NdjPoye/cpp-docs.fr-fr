---
title: "Erreur du compilateur C3536 | Microsoft Docs"
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
  - "C3536"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3536"
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3536
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

« symbole » : ne peut pas être utilisé avant d'être initialisé  
  
 Le symbole indiqué ne peut pas être utilisé avant d'être initialisé.  Dans la pratique, cela signifie qu'une variable ne peut pas être utilisée pour s'initialiser.  
  
### Pour corriger cette erreur  
  
1.  N'initialisez pas de variable avec elle\-même.  
  
## Exemple  
 L'exemple suivant donne C3536 parce que chaque variable est initialisée avec elle\-même.  
  
```  
// C3536.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto a = a;     //C3536  
   auto b = &b;    //C3536  
   auto c = c + 1; //C3536  
   auto* d = &d;   //C3536  
   auto& e = e;    //C3536  
   return 0;  
};  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)