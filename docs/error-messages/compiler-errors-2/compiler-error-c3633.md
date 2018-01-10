---
title: Erreur du compilateur C3633 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3633
dev_langs: C++
helpviewer_keywords: C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b88a5008b0703f99d7eefa3892b4ee263fea9d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3633"></a>Erreur du compilateur C3633
Impossible de définir 'membre' en tant que membre de 'type' managé  
  
Membres de données de classe de référence CLR ne peut pas être d’un type non POD C++.  Vous ne pouvez instancier un type POD dans un type CLR.  Par exemple, un type POD ne peut pas contenir un constructeur de copie ou un opérateur d’assignation.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère des C3633.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  
