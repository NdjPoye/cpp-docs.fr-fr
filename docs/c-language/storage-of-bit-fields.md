---
title: Stockage des champs de bits | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f223ff90517b6365645a861420ebe1985f994d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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