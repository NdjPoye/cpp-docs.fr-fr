---
title: Compilateur avertissement (niveau 1) C4667 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4667
dev_langs: C++
helpviewer_keywords: C4667
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fd488cc755bf805ec9af469cabab77108565f37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4667"></a>Avertissement du compilateur (niveau 1) C4667
'fonction' : aucun modèle de fonction défini correspondant de l’instanciation n’imposée  
  
 Vous ne pouvez pas instancier un modèle de fonction qui n’a pas été déclaré.  
  
 L’exemple suivant génère C4667 :  
  
```  
// C4667a.cpp  
// compile with: /LD /W1  
template  
void max(const int &, const int &); // C4667 expected  
```  
  
 Pour éviter cet avertissement, commencez par déclarer le modèle de fonction :  
  
```  
// C4667b.cpp  
// compile with: /LD  
// Declare the function template  
template<typename T>  
const T &max(const T &a, const T &b) {  
   return (a > b) ? a : b;  
}  
// Then forcibly instantiate it with a desired type ... i.e. 'int'  
//  
template  
const int &max(const int &, const int &);  
```