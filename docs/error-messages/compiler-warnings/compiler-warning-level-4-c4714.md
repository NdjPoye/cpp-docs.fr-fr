---
title: "Avertissement du compilateur (niveau 4) C4714 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4714"
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 4) C4714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fonction 'fonction' marquée comme \_\_forceinline non inline  
  
 La fonction donnée a été sélectionnée pour l'expansion inline, mais le compilateur n'a pas effectué la fonctionnalité inline.  
  
 Bien que `__forceinline` soit une indication plus forte que `__inline` pour le compilateur, la fonctionnalité inline est toujours appliquée à la discrétion du compilateur, mais aucun heuristique n'est utilisé pour déterminer les avantages d'appliquer la fonctionnalité inline à cette fonction.  
  
 Dans certains cas, le compilateur n'appliquera pas la fonctionnalité inline à une fonction particulière pour des raisons mécaniques.  Par exemple, le compilateur n'appliquera pas la fonctionnalité inline à :  
  
-   Une fonction si cela conduirait à mélanger à la fois SEH et C\+\+ EH.  
  
-   Certaines fonctions avec des objets construits par copie passés par une valeur lorsque \-GX\/EHs\/EHa est actif.  
  
-   Des fonctions qui retournent un objet déroulable par une valeur lorsque \-GX\/EHs\/EHa est actif.  
  
-   Des fonctions avec un assembly inline lors d'une compilation sans \-Og\/Ox\/O1\/O2.  
  
-   Des fonctions avec une liste d'arguments variable.  
  
-   Une fonction avec une instruction **try** \(gestion des exceptions C\+\+\).  
  
 L'exemple suivant génère l'erreur C4714 :  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```