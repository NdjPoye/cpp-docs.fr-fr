---
title: "Avertissement du compilateur (niveau 4) C4706 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4706"
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 4) C4706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

assignation au sein d'une expression conditionnelle  
  
 La valeur testée dans une expression conditionnelle était le résultat d'une assignation.  
  
 Une assignation possède une valeur \(la valeur à gauche de l'assignation\) qui peut être légalement utilisée dans une autre expression, y compris une expression de test.  
  
 L'exemple suivant génère l'erreur C4706 :  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 L'avertissement aura lieu même si vous doublez les parenthèses autour de la condition testée :  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 Si vous avez l'intention de tester une relation et non pas d'effectuer une assignation, utilisez l'opérateur `==`.  La ligne suivante, par exemple, teste si a et b sont égaux :  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 Si vous prévoyez d'utiliser la valeur testée comme résultat d'une assignation, vérifiez que l'assignation est différente de zéro.  Le code suivant, par exemple, ne générera pas cet avertissement :  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```