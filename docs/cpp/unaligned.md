---
title: __unaligned | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
- __unaligned
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9f899add9a1306344a10840220f3b7504e917d91
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="unaligned"></a>__unaligned
Lorsque vous déclarez un pointeur avec le modificateur `__unaligned`, le compilateur suppose que le pointeur adresse des données non alignées. Par conséquent, pour une application qui cible un ordinateur de la famille de processeurs Itanium (IPF), le compilateur génère un code qui lit les données non alignées octet par octet.  
  
## <a name="remarks"></a>Remarques  
 Le `__unaligned` modificateur n’est valide pour le [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] et [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] compilateurs, mais affecte uniquement les applications qui ciblent un ordinateur IPF. Ce modificateur décrit l'alignement des données adressées uniquement ; le pointeur lui-même est considéré comme aligné.  
  
 Le [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] processeur génère une erreur d’alignement lorsqu’il accède aux données mal alignées et le temps de traitement de l’erreur réduit les performances. Utilisez le modificateur `__unaligned` pour imposer au processeur de lire les données octet par octet, afin d'éviter l'erreur. Ce modificateur n’est pas obligatoire pour [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] applications, car le [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] processeur gère les données mal alignées sans erreur.  
  
 Pour plus d'informations sur l'alignement, consultez :  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__alignof, opérateur](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [/Zp (alignement des membres de la structure)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Exemples d’alignement de structure](../build/examples-of-structure-alignment.md)  
  
## <a name="example"></a>Exemple  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)
