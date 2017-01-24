---
title: "Pourquoi les nombres &#224; virgule flottante peuvent manquer de pr&#233;cision | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DBL_EPSILON (constante)"
  - "chiffres à virgule flottante, précision"
  - "FLT_EPSILON (constante)"
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Pourquoi les nombres &#224; virgule flottante peuvent manquer de pr&#233;cision
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les valeurs décimales à virgule flottante n'ont généralement pas une représentation binaire exacte.  Il s'agit d'un effet secondaire lié à la manière dont l'UC représente les données à virgule flottante.  Pour cette raison, vous pouvez constater une certaine perte de précision, et certaines opérations à virgule flottante peuvent donner lieu à des résultats inattendus.  
  
 Ce comportement est le résultat de l'un des phénomènes suivants :  
  
-   la représentation binaire du nombre décimal n'est peut\-être pas exacte ;  
  
-   il existe une discordance de type entre les nombres utilisés \(par exemple, un mélange de nombres à virgule flottante et de nombres en double précision\).  
  
 Pour remédier à cette situation, la plupart des programmeurs s'assurent que la valeur est supérieure ou inférieure à ce qui est nécessaire, ou ils obtiennent et utilisent une bibliothèque de type décimal codé binaire \(BCD, Binary Coded Decimal\) qui préserve la précision.  
  
 La représentation binaire des valeurs à virgule flottante affecte la précision et l'exactitude des calculs à virgule flottante.  Microsoft Visual C\+\+ utilise le [format à virgule flottante IEEE](../../build/reference/ieee-floating-point-representation.md).  
  
## Exemple  
  
```  
// Floating-point_number_precision.c  
// Compile options needed: none. Value of c is printed with a decimal   
// point precision of 10 and 6 (printf rounded value by default) to   
// show the difference  
#include <stdio.h>  
  
#define EPSILON 0.0001   // Define your own tolerance  
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))  
  
int main() {  
   float a, b, c;  
  
   a = 1.345f;  
   b = 1.123f;  
   c = a + b;  
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result  
   if (c == 2.468)            // Comment this line for correct result  
      printf_s("They are equal.\n");  
   else  
      printf_s("They are not equal! The value of c is %13.10f "  
                "or %f",c,c);  
}  
```  
  
  **Elle ne sont pas égales \!  La valeur de c est 2.4679999352 ou 2.46800**    
## Commentaires  
 Pour EPSILON, vous pouvez utiliser les constantes FLT\_EPSILON, dont la définition en notation à virgule flottante est 1,192092896e\-07F, ou DBL\_EPSILON, dont la définition en notation double précision est 2,2204460492503131e\-016.  Vous devez inclure float.h pour ces constantes.  Ces constantes sont définies comme étant le plus petit nombre positif x, ce qui fait que x\+1.0 n'est pas égal à 1.0.  Dans la mesure où il s'agit d'un très petit nombre, vous devez employer une tolérance définie par l'utilisateur pour les calculs impliquant de très grands nombres.  
  
## Voir aussi  
 [Optimisation du code](../../build/reference/optimizing-your-code.md)