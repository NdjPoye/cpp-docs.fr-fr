---
title: "Erreur du compilateur C2093 | Microsoft Docs"
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
  - "C2093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2093"
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2093
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable1' : ne peut pas être initialisée à l'aide de l'adresse de la variable automatique 'variable2'  
  
 Lors de la compilation avec [\/Za](../../build/reference/za-ze-disable-language-extensions.md), le programme a tenté d'utiliser l'adresse d'une variable automatique comme initialiseur.  
  
 L'exemple suivant génère l'erreur C2093 :  
  
```  
// C2093.c  
// compile with: /Za /c  
void func() {  
   int li;   // an implicit auto variable  
   int * s[]= { &li };   // C2093 address is not a constant  
  
   // OK  
   static int li2;  
   int * s2[]= { &li2 };  
}  
```