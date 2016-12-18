---
title: "Constantes globales en C++ | Microsoft Docs"
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
  - "constantes, globaux"
  - "constantes globales"
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Constantes globales en C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les constantes globales en C\+\+ sont à liaison statique.  Cela n'est pas le cas en C.  Si vous tentez d'utiliser une constante globale en C\+\+ dans plusieurs fichiers, vous obtenez une erreur externe non résolue.  Le compilateur optimise les constantes globales, et ne laisse pas d'espace réservé pour la variable.  
  
 Cette erreur peut être résolue en incluant les initialisations de constantes dans un fichier d'en\-tête pour inclure cet en\-tête dans vos fichiers CPP quand c'est nécessaire, comme s'il s'agissait d'un prototype de fonction.  Une autre possibilité consiste à rendre la variable non constante et à utiliser une référence à une constante pour l'utiliser.  
  
 L'exemple suivant génère l'erreur C2019 :  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 Ensuite,  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## Voir aussi  
 [Erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)