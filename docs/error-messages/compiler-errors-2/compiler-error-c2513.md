---
title: "Erreur du compilateur C2513 | Microsoft Docs"
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
  - "C2513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2513"
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : aucune variable déclarée avant '\='  
  
 Le spécificateur de type apparaît dans la déclaration sans identificateur de variable.  
  
 L'exemple suivant génère l'erreur C2513 :  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual Studio .NET 2003 : initialisation d'un typedef dorénavant interdite.  L'initialisation d'un typedef est interdite par le standard et génère maintenant une erreur du compilateur.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 Une alternative consisterait à supprimer `typedef` pour définir une variable avec une liste d'initialiseurs d'agrégat, mais cela n'est pas recommandé, car une variable portant le même nom que le type serait créée et masquerait le nom du type.