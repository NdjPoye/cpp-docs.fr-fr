---
title: "Point de d&#233;claration en C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "point de déclaration"
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Point de d&#233;claration en C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un nom est considéré comme déclaré immédiatement après son déclarateur mais avant son initialiseur \(facultatif\).  \(Pour plus d'informations sur les déclarateurs, consultez [Déclarateurs](http://msdn.microsoft.com/fr-fr/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).\)  
  
 Considérez cet exemple :  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Si le point de déclaration avait lieu *après* l'initialisation, alors la variable locale `dVar` serait initialisée à 7,0, la valeur de la variable globale `dVar`.  Toutefois, comme ce n'est pas le cas, `dVar` est initialisé avec une valeur non définie.  
  
## Voir aussi  
 [Portée](../cpp/scope-visual-cpp.md)