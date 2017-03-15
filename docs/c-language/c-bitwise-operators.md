---
title: "Op&#233;rateurs de bits C | Microsoft Docs"
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
  - "& (opérateur), opérateurs de bits"
  - "^ (opérateur)"
  - "^ (opérateur), opérateurs de bits"
  - "| (opérateur), opérateurs de bits"
  - "et commercial (opérateur &)"
  - "AND (opérateur)"
  - "opérateurs de bits"
  - "opérateurs de bits, Visual C"
  - "opérateurs (C), au niveau du bit"
ms.assetid: e22127b1-9a2d-4876-b01d-c8f72cec3317
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Op&#233;rateurs de bits C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs de bits exécutent l'opération de bits ET \(**&**\), de bits OU\-Exclusif \(**^**\), et de bits OU\-inclusif \(       **&#124;** \) opérations.  
  
 **Syntaxe**  
  
 *expression ET*:  
 *Expressions d'égalité*  
  
 *expression ET* **&**  *expression d'égalité*  
  
 *expression OU\-exclusif*:  
 *Expression ET*  
  
 *expression OU\-exclusif*  **^**  *expression ET*  
  
 *expression OU\-inclusif*:  
 *expression OU\-exclusif*  
  
 *expression OU\-inclusif* &#124; *expression OU\-exclusif*  
  
 Les opérandes des opérateurs de bits doivent avoir des types intégraux, mais leurs types peuvent être différents.  Ces opérateurs exécutent les conversions arithmétiques habituelles ; le type du résultat est le type des opérandes après conversion.  
  
 Les opérateurs de bits C sont décrits ci\-dessous :  
  
|Opérateur|Description|  
|---------------|-----------------|  
|**&**|L'opérateur de bits ET compare chaque bit de son premier opérande au bit correspondant de son second opérande.  Si les deux bits sont 1, le bit de résultat correspondant a la valeur 1.  Sinon, le bit correspondant de résultat a la valeur 0.|  
|**^**|L'opérateur de bits OU\-exclusif compare chaque bit de son premier opérande au bit correspondant de son second opérande.  Si un bit est 0 et l'autre bits est 1, le bit de résultat correspondant a la valeur 1.  Sinon, le bit de résultat correspondant a la valeur 0.|  
|**&#124;**|L'opérateur de bits OU\-inclusif compare chaque bit de son premier opérande au bit correspondant de son second opérande.  Si l'un des bits est 1, le bit de résultat correspondant a la valeur 1.  Sinon, le bit de résultat correspondant a la valeur 0.|  
  
## Exemples  
 Ces déclarations sont utilisées pour les trois exemples suivants :  
  
```  
short i = 0xAB00;  
short j = 0xABCD;  
short n;  
  
n = i & j;  
```  
  
 Le résultat assignée à `n` dans ce premier exemple est identique à `i` \(hexadécimale 0xAB00\).  
  
```  
n = i | j;  
  
n = i ^ j;  
```  
  
 L'opérateur de bits OU\-inclusif dans le deuxième exemple produit la valeur 0xABCD \(hexadécimal\), alors que l'opérateur de bits OU\-exclusif dans le troisième exemple produit 0xCD \(hexadécimal\).  
  
 **Spécifique à Microsoft**  
  
 Les résultats de l'opération de bits sur les entiers signés est une implémentation définie selon la norme C ANSI.  Pour le compilateur C Microsoft, les opérations de bits sur les entiers signés fonctionnent de manières identiques aux opérations de bits sur des entiers non signés.  Par exemple, `-16 & 99` peut aussi être exprimé en binaire comme  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Le résultat de l'opérateur de bit ET est la décimale 96.  
  
 **END Spécifique à Microsoft**  
  
## Voir aussi  
 [Opérateur de bits AND : &](../cpp/bitwise-and-operator-amp.md)   
 [Opérateur de bits OR exclusif : ^](../cpp/bitwise-exclusive-or-operator-hat.md)   
 [Opérateur de bits OR inclusif : &#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)