---
title: "Stockage des champs de bits | Microsoft Docs"
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
  - "C"
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Stockage des champs de bits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.5.2.1** L'ordre d'allocation des champs de bits dans un int  
  
 Les champs de bits sont alloués dans un entier du bit de poids le plus faible au bit de poids le plus fort.  Dans le code suivant  
  
```  
struct mybitfields  
{  
   unsigned a : 4;  
   unsigned b : 5;  
   unsigned c : 7;  
} test;  
  
int main( void )  
{  
   test.a = 2;  
   test.b = 31;  
   test.c = 0;  
}  
```  
  
 les bits sont disposés comme suit :  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 Les processeurs 80x86 stockent l'octet faible des valeurs entières avant l'octet fort. L'entier 0x01F2 ci\-dessus serait stocké en mémoire physique comme 0xF2 suivi de 0x01.  
  
## Voir aussi  
 [Structures, unions, énumérations et champs de bits](../c-language/structures-unions-enumerations-and-bit-fields.md)