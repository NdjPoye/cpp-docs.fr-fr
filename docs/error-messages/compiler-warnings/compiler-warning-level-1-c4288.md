---
title: Compilateur avertissement (niveau 1) C4288 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4288
dev_langs: C++
helpviewer_keywords: C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: abbc9ba0a41a4961c49cffca6c10ff9a4e4e1437
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4288"></a>Avertissement du compilateur (niveau 1) C4288
extension non standard utilisée : 'var' : variable de contrôle de boucle déclarée dans la boucle for est utilisée en dehors de la portée de la boucle ; Il est en conflit avec la déclaration de la portée externe  
  
 Lors de la compilation avec [/Ze](../../build/reference/za-ze-disable-language-extensions.md) et **/Zc:forscope-**, une variable déclarée dans une **pour** boucle a été utilisée après la [pour](../../cpp/for-statement-cpp.md)-portée de la boucle. Une extension Microsoft du langage C++ permet à cette variable de rester dans la portée et C4288 vous rappelle que la première déclaration de la variable n’est pas utilisée.  
  
 Consultez [/Zc : forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) pour plus d’informations sur la spécification de l’extension Microsoft de **pour** boucles avec/Ze.  
  
 L’exemple suivant génère l’erreur C4288 :  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```