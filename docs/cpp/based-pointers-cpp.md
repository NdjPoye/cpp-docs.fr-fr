---
title: "Pointeurs bas&#233;s sur (C++) | Microsoft Docs"
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
  - "__based"
  - "__based_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__based (mot clé) (C++)"
  - "based (pointeurs)"
  - "pointeurs, based"
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pointeurs bas&#233;s sur (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le mot clé `__based` vous permet de déclarer des pointeurs basés sur pointeurs \(pointeurs décalés par rapports aux pointeurs existants\).  
  
## Syntaxe  
  
```  
  
type __based( base ) declarator   
```  
  
## Notes  
 Les adresses de pointeurs basés sur pointeurs sont la seule forme du mot clé `__based` valide dans les compilations 32 bits ou 64 bits.  Pour le compilateur Microsoft C\/C\+\+ 32 bits, un pointeur based est un décalage de 32 bits par rapport à une base de pointeur 32 bits.  Une restriction similaire s'applique pour les environnements 64 bits, où un pointeur based est un décalage de 64 bits par rapport à la base 64 bits.  
  
 Les pointeurs basés sur pointeurs peuvent par exemple être utilisés pour des identificateurs persistants qui contiennent des pointeurs.  Une liste liée composée de pointeurs basés sur un pointeur peut être enregistrée sur le disque, puis rechargée dans un autre emplacement mémoire, et les pointeurs restent valides.  Par exemple :  
  
```  
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Le pointeur `vpBuffer` reçoit l'adresse de la mémoire allouée à un point ultérieur dans le programme.  La liste liée est déplacée par rapport à la valeur de `vpBuffer`.  
  
> [!NOTE]
>  Les identificateurs persistants contenant des pointeurs peuvent également être élaborés à l'aide de [fichiers mappés en mémoire](http://msdn.microsoft.com/library/windows/desktop/aa366556).  
  
 Lors du déréférencement d'un pointeur based, la base doit être spécifiée explicitement ou connue implicitement via la déclaration.  
  
 Pour assurer la compatibilité avec les versions antérieures, **\_based** est synonyme de `__based`.  
  
## Exemple  
 Le code suivant illustre comment modifier un pointeur based en modifiant sa base.  
  
```  
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
  **1**  
**2**  
**10**  
**11**   
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [alloc\_text](../preprocessor/alloc-text.md)