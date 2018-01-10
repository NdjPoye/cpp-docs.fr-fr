---
title: Stockage des champs de bits | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1be04ba4c68b2629a5e765788af95a203ae06b34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-bit-fields"></a>Stockage des champs de bits
**ANSI 3.5.2.1** L'ordre d'allocation des champs de bits dans un int  
  
 Les champs de bits sont alloués dans un entier du bit de poids le plus faible au bit de poids le plus fort. Dans le code suivant  
  
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
  
 Les processeurs 80x86 stockent l'octet faible des valeurs entières avant l'octet fort. L'entier 0x01F2 ci-dessus serait stocké en mémoire physique comme 0xF2 suivi de 0x01.  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, unions, énumérations et champs de bits](../c-language/structures-unions-enumerations-and-bit-fields.md)