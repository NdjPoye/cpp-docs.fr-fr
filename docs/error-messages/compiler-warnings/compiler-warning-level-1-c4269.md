---
title: "Avertissement du compilateur (niveau 1) C4269 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4269"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4269"
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4269
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : les données automatiques 'const' initialisées avec le constructeur par défaut généré par le compilateur produisent des résultats incertains  
  
 Une instance automatique **const** d'une classe non triviale est initialisée avec un constructeur par défaut généré par le compilateur.  
  
## Exemple  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 Cette instance de la classe est générée sur la pile, donc la valeur initiale de `m_data` peut être quelconque.  Du fait que c'est une instance de **const**, la valeur de `m_data` ne peut jamais être modifiée.