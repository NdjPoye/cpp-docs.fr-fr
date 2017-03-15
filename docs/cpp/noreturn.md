---
title: "noreturn | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noreturn_cpp"
  - "noreturn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), noreturn"
  - "noreturn __declspec (mot clé)"
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# noreturn
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Cet attribut `__declspec` indique au compilateur qu'une fonction ne retourne pas.  Par conséquent, le compilateur sait que le code qui suit un appel à une fonction **\_\_declspec\(noreturn\)** est inaccessible.  
  
 Si le compilateur recherche une fonction avec un chemin d'accès au contrôle qui ne retourne pas de valeur, il génère un avertissement \(C4715\) ou le message d'erreur \(C2202\).  Si le chemin d'accès au contrôle ne peut pas être atteint en raison d'une fonction qui ne retourne jamais, vous pouvez utiliser **\_\_declspec\(noreturn\)** pour éviter cet avertissement ou cette erreur.  
  
> [!NOTE]
>  L'ajout de **\_\_declspec\(noreturn\)** à une fonction censée retourner peut entraîner un comportement non défini.  
  
## Exemple  
 Dans l'exemple suivant, la clause **else** ne contient pas d'instruction return.  La déclaration `fatal` en tant que **\_\_declspec\(noreturn\)** évite une erreur ou un message d'avertissement.  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)