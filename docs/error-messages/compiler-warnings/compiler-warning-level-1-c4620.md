---
title: Compilateur avertissement (niveau 1) C4620 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4620
dev_langs:
- C++
helpviewer_keywords:
- C4620
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f550a857f1799e32d599231348123e3f85a0dfd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4620"></a>Avertissement du compilateur (niveau 1) C4620
aucune forme suffixée de l’opérateur 'operator ++' trouvée pour le type 'type' ; utilisez la forme préfixée  
  
 Aucun opérateur d’incrément postfix n’est défini pour le type donné. Le compilateur a utilisé l’opérateur de préfixe surchargé.  
  
 Pour éviter cet avertissement, vous pouvez définir un opérateur `++` postfix. Créez une version à deux arguments de l’opérateur `++` , comme indiqué ici :  
  
```  
// C4620.cpp  
// compile with: /W1  
class A  
{  
public:  
   A(int nData) : m_nData(nData)  
   {  
   }  
  
   A operator++()  
   {  
      m_nData -= 1;  
      return *this;  
   }  
  
   // A operator++(int)  
   // {  
   //    A tmp = *this;  
   //    m_nData -= 1;  
   //    return tmp;  
   // }  
  
private:  
   int m_nData;  
};  
  
int main()  
{  
   A a(10);  
   ++a;  
   a++;   // C4620  
}  
```