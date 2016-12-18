---
title: "Corps de fonction ou variable manquant | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "corps de fonction"
  - "variables, manquantes"
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Corps de fonction ou variable manquant
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avec seulement un prototype de fonction, le compilateur peut poursuivre sans erreur, mais l'éditeur de liens ne peut pas résoudre un appel à une adresse parce qu'il n'y a pas de code de fonction ou d'espace réservé pour la variable.  Vous ne verrez pas cette erreur tant que vous n'aurez pas créé un appel à la fonction que l'éditeur de liens ait à résoudre.  
  
## Exemple  
 L'appel de fonction dans main provoque l'erreur LNK2019, car le prototype permet au compilateur de considérer que la fonction existe.  L'éditeur de liens découvre que ce n'est pas le cas.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## Exemple  
 En C\+\+, vérifiez que vous incluez l'implémentation d'une fonction spécifique pour une classe et pas seulement un prototype dans la définition de la classe.  Si vous définissez la classe en dehors du fichier d'en\-tête, prenez soin d'inclure le nom de la classe avant la fonction \(`Classname``::``memberfunction`\).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## Voir aussi  
 [Erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)