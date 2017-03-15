---
title: "novtable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "novtable"
  - "novtable_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), novtable"
  - "novtable __declspec (mot clé)"
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# novtable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 C'est un attribut étendu `__declspec`.  
  
 Cette forme de `__declspec` peut être appliquée à toute déclaration de classe, mais ne doit être appliquée qu'aux classes d'interface pures, c'est\-à\-dire aux classes qui ne seront jamais instanciées toutes seules.  `__declspec` arrête la génération de code par le compilateur pour initialiser le vfptr dans le\(s\) constructeur\(s\) et le destructeur de la classe.  Dans de nombreux cas, cela supprime les seules références à la vtable qui sont associés à la classe et, par conséquent, l'éditeur de liens supprimera cette vtable.  L'utilisation de cette forme de `__declspec` peut entraîner une réduction considérable de la taille du code.  
  
 Si vous essayez d'instancier une classe marquée avec `novtable` puis d'accéder à un membre de classe, vous recevrez une violation d'accès.  
  
## Exemple  
  
```  
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
  **In Y**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)