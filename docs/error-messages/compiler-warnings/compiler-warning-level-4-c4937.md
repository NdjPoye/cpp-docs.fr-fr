---
title: Compilateur avertissement (niveau 4) C4937 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4937
dev_langs: C++
helpviewer_keywords: C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 824eed0550fd684232d829678eae64b1acfa9a37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4937"></a>Avertissement du compilateur (niveau 4) C4937
impossible de distinguer 'text1' et 'text2' comme arguments de 'directive'  
  
 Compte tenu de la méthode utilisée par le compilateur pour traiter les arguments aux directives, il est impossible de différencier les noms qui ont une signification pour le compilateur, notamment les mots clés avec plusieurs représentations textuelles (formes à un ou deux traits de soulignement).  
  
 Exemples de ces chaînes sont __cdecl et \__forceinline.  Sous /Za, notez que seules les formes à deux traits de soulignement sont activées.  
  
 L’exemple suivant génère l’avertissement C4937 :  
  
```  
// C4937.cpp  
// compile with: /openmp /W4  
#include "omp.h"  
int main() {  
   #pragma omp critical ( __leave )   // C4937  
   ;  
  
   // OK  
   #pragma omp critical ( leave )  
   ;  
}  
```