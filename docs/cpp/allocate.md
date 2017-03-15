---
title: "allocate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "allocate"
  - "allocate_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), allouer"
  - "allouer mot clé __declspec"
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# allocate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le spécificateur de déclaration **allocate** désigne un segment de données dans lequel l'élément de données sera alloué.  
  
## Syntaxe  
  
```  
  
__declspec(allocate("  
segname  
")) declarator  
```  
  
## Notes  
 Le nom *segname* doit être déclaré à l'aide de l'un des pragmas suivants :  
  
-   [code\_seg](../preprocessor/code-seg.md)  
  
-   [const\_seg](../preprocessor/const-seg.md)  
  
-   [data\_seg](../preprocessor/data-seg.md)  
  
-   [init\_seg](../preprocessor/init-seg.md)  
  
-   [section](../preprocessor/section.md)  
  
## Exemple  
  
```  
// allocate.cpp  
#pragma section("mycode", read)  
__declspec(allocate("mycode"))  int i = 0;  
  
int main() {  
}  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)