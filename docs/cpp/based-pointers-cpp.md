---
title: En fonction des pointeurs (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __based
- __based_cpp
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6cc2e45574d30ae1a544da78a4f7a75321a1156
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="based-pointers-c"></a>Pointeurs basés sur (C++)
**Section spécifique à Microsoft**  
  
 Le mot clé `__based` vous permet de déclarer des pointeurs basés sur pointeurs (pointeurs décalés par rapports aux pointeurs existants).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
type __based( base ) declarator   
```  
  
## <a name="remarks"></a>Notes  
 Les adresses de pointeurs basés sur pointeurs sont la seule forme du mot clé `__based` valide dans les compilations 32 bits ou 64 bits. Pour le compilateur Microsoft C/C++ 32 bits, un pointeur based est un décalage de 32 bits par rapport à une base de pointeur 32 bits. Une restriction similaire s'applique pour les environnements 64 bits, où un pointeur based est un décalage de 64 bits par rapport à la base 64 bits.  
  
 Les pointeurs basés sur pointeurs peuvent par exemple être utilisés pour des identificateurs persistants qui contiennent des pointeurs. Une liste liée composée de pointeurs basés sur un pointeur peut être enregistrée sur le disque, puis rechargée dans un autre emplacement mémoire, et les pointeurs restent valides. Par exemple :  
  
```  
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Le pointeur `vpBuffer` reçoit l'adresse de la mémoire allouée à un point ultérieur dans le programme. La liste liée est déplacée par rapport à la valeur de `vpBuffer`.  
  
> [!NOTE]
>  Les identificateurs persistants contenant des pointeurs peuvent également être accomplies en utilisant [fichiers mappés en mémoire](http://msdn.microsoft.com/library/windows/desktop/aa366556).  
  
 Lors du déréférencement d'un pointeur based, la base doit être spécifiée explicitement ou connue implicitement via la déclaration.  
  
 Pour la compatibilité avec les versions précédentes, **_based** est un synonyme de `__based`.  
  
## <a name="example"></a>Exemple  
 Le code suivant illustre comment modifier un pointeur based en modifiant sa base.  
  
```  
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
```Output  
1  
2  
10  
11  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [alloc_text](../preprocessor/alloc-text.md)