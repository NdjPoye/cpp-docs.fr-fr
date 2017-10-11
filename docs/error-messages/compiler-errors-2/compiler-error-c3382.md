---
title: Erreur du compilateur C3382 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 782e5c4cc61294dbdaecbd63ff5c6031d387f843
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3382"></a>Erreur du compilateur C3382
'sizeof' n'est pas pris en charge avec /clr:safe  
  
 Le fichier de sortie d’une compilation **/clr:safe** est un fichier de type sécurisé vérifiable. De plus, sizeof n’est pas pris en charge, car la valeur de retour de l’opérateur sizeof est size_t, dont la taille varie selon le système d’exploitation.  
  
 Pour plus d'informations, consultez  
  
-   [sizeof, opérateur](../../cpp/sizeof-operator.md)  
  
-   [/CLR (Compilation pour le common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Problèmes courants de migration vers Visual C++ 64 bits](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3382 :  
  
```  
// C3382.cpp  
// compile with: /clr:safe  
int main() {  
   sizeof( char );   // C3382  
}  
```
