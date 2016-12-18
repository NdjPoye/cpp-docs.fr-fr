---
title: "Avertissement du compilateur (niveau 1) C4540 | Microsoft Docs"
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
  - "C4540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4540"
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

utilisation de dynamic\_cast pour convertir en une base ambiguë ou inaccessible ; le test d'exécution échouera \('type1' à 'type2'\)  
  
 Vous avez utilisé `dynamic_cast` pour convertir d'un type en un autre.  Le compilateur a déterminé que le cast échouerait toujours \(retournerait **NULL**\) parce qu'une classe de base est inaccessible \(par exemple `private`\) ou ambiguë \(apparaît plus d'une fois dans la hiérarchie de classes, par exemple\).  
  
 Le code ci\-dessous présente un exemple de cet avertissement.  La classe **B** est dérivée de ma classe **A**.  Le programme utilise `dynamic_cast` pour effectuer un cast de la classe **B** \(classe dérivée\) en la classe **A**, ce qui échouera toujours parce que la classe **B** est `private` et donc inaccessible.  Pour remédier à cet avertissement, remplacez l'accès de **A** par **public**.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```