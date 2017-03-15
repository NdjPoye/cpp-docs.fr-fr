---
title: "Avertissement du compilateur (niveau 1) C4091 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4091"
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'MotClé' : ignoré à gauche de 'type' quand aucune variable n'est déclarée  
  
 Le compilateur a détecté une situation dans laquelle l'utilisateur attendait probablement la déclaration d'une variable, mais le compilateur n'a pas pu la déclarer.  
  
## Exemple  
 Un attribut `__declspec` au début d'une déclaration de type défini par l'utilisateur s'applique à la variable de ce type.  L'erreur C4091 indique qu'aucune variable n'est déclarée.  L'exemple suivant génère l'erreur C4091 :  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## Exemple  
 Si un identificateur est un typedef, il ne peut pas également être un nom de variable.  L'exemple suivant génère l'erreur C4091 :  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```