---
title: "void (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "void"
  - "void_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions (C++), void"
  - "pointeurs, void"
  - "void (mot clé) (C++)"
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# void (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand il est utilisé en tant que type de retour de fonction, le mot clé `void` spécifie que la fonction ne retourne pas de valeur.  Quand il est utilisé pour la liste des paramètres d'une fonction, void spécifie que la fonction ne prend aucun paramètre.  Quand il est utilisé dans la déclaration d'un pointeur, void spécifie que le pointeur est « universel ».  
  
 Si le type de pointeur est **void \***, le pointeur peut pointer vers n'importe quelle variable qui n'est pas déclarée avec le mot clé **const** ou `volatile`.  Un pointeur void ne peut pas être déréférencé, sauf s'il fait l'objet d'un cast en un autre type.  Un pointeur void peut être converti en tout autre type de pointeur de données.  
  
 Un pointeur void peut pointer vers une fonction, mais pas vers un membre de classe en C\+\+.  
  
 Vous ne pouvez pas déclarer une variable de type void.  
  
## Exemple  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Pointeurs vers type void](../misc/pointers-to-type-void.md)   
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)