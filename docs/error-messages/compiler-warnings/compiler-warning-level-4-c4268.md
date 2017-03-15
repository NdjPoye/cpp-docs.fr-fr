---
title: "Avertissement du compilateur (niveau 4) C4268 | Microsoft Docs"
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
  - "C4268"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4268"
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4268
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : les données 'const' static\/global initialisées avec le constructeur par défaut généré par le compilateur remplissent l'objet de zéros  
  
 Une instance de type **const** globale ou statique d'une classe non triviale est initialisée avec un constructeur par défaut généré par le compilateur.  
  
## Exemple  
  
```  
// C4268.cpp  
// compile with: /c /LD /W4  
class X {  
public:  
   int m_data;  
};  
  
const X x1;   // C4268  
```  
  
 Cette instance de la classe est **const**, donc la valeur de `m_data` ne peut pas être modifiée.