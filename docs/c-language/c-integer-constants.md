---
title: "Constantes enti&#232;res C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "constantes entières"
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Constantes enti&#232;res C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une « constante Integer » est un nombre décimal \(base 10\), octal \(base 8\) ou hexadécimal \(base 16\) qui représente une valeur intégrale.  Utilisez les constantes Integer pour représenter des valeurs entières qui ne peuvent pas être modifiées.  
  
## Syntaxe  
 *integer\-constant* :  
 *decimal\-constant integer\-suffix*  opt  
  
 *octal\-constant integer\-suffix*  opt  
  
 *hexadecimal\-constant integer\-suffix*  opt  
  
 *decimal\-constant* :  
 *nonzero\-digit*  
  
 *decimal\-constant digit*  
  
 *octal\-constant* :  
 **0**  
  
 *octal\-constant octal\-digit*  
  
 *hexadecimal\-constant* :  
 **0x**  *hexadecimal\-digit*  
  
 **0X**  *hexadecimal\-digit*  
  
 *hexadecimal\-constant hexadecimal\-digit*  
  
 *nonzero\-digit* : un des éléments suivants :  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal\-digit* : un des éléments suivants :  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal\-digit* : un des éléments suivants :  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *integer\-suffix* :  
 *unsigned\-suffix long\-suffix*  opt  
  
 *long\-suffix unsigned\-suffix*  opt  
  
 *unsigned\-suffix* : un des éléments suivants :  
 **u U**  
  
 *long\-suffix* : un des éléments suivants :  
 **l L**  
  
 *64\-bit integer\-suffix* :  
 **i64**  
  
 Les constantes Integer sont positives, à moins d'être précédées du signe moins \(**–**\).  Le signe moins est interprété comme l'opérateur de négation arithmétique unaire. \(Pour plus d'informations sur cet opérateur, consultez [Opérateurs arithmétiques unaires](../c-language/unary-arithmetic-operators.md).\)  
  
 Si une constante Integer commence par **0x** ou **0X**, elle est hexadécimale.  Si elle commence par le chiffre **0**, elle est octale.  Sinon, elle est supposée être décimale.  
  
 Les lignes suivantes sont équivalentes :  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 Aucun espace blanc ne peut séparer les chiffres d'une constante Integer.  Ces exemples illustrent des constantes décimales, octales et hexadécimales valides.  
  
```  
/* Decimal Constants */  
10  
132  
32179  
  
/* Octal Constants */  
012  
0204  
076663  
  
/* Hexadecimal Constants */  
0xa or 0xA  
0x84  
0x7dB3 or 0X7DB3  
```  
  
## Voir aussi  
 [Constantes C](../c-language/c-constants.md)