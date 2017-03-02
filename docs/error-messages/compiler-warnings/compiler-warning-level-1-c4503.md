---
title: "L’erreur C4503 (niveau 1) d’avertissement de compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: f999fcb73860bfd2fabb3484e78f313a32240dee
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4503"></a>Avertissement du compilateur (niveau 1) C4503
'identificateur' : longueur du nom dépassée, décoré nom a été tronqué.  
  
 Le nom décoré était plus long que la limite du compilateur (4096) et a été tronqué. Pour éviter cet avertissement et la troncature, réduisez le nombre d’arguments ou la longueur du nom des identificateurs utilisés.  
  
 Une situation où cet avertissement est émis est lorsque votre code contient des modèles spécialisés à plusieurs reprises sur des modèles.  Par exemple, une table de tables (à partir de la bibliothèque C++ Standard).  Dans ce cas, vous pouvez rendre vos typedefs un type (struct, par exemple) qui contient le mappage.  
  
 Toutefois, vous pourriez ne pas restructurer votre code.  Il est possible d’expédier une application qui génère l’erreur C4503, mais si vous obtenez des erreurs de liaison sur un symbole tronqué, il sera plus difficile de déterminer le type du symbole dans l’erreur.  Débogage sera également plus difficile ; le débogueur aura également nom de symbole à taper le nom de mappage, il est difficile.  Toutefois, l’exactitude du programme n’est pas affecté par le nom tronqué.  
  
 L’exemple suivant génère l’erreur C4503 :  
  
```  
// C4503.cpp  
// compile with: /W1 /EHsc /c  
// C4503 expected  
#include <string>  
#include <map>  
  
class Field{};  
  
typedef std::map<std::string, Field> Screen;  
typedef std::map<std::string, Screen> WebApp;  
typedef std::map<std::string, WebApp> WebAppTest;  
typedef std::map<std::string, WebAppTest> Hello;  
Hello MyWAT;  
```  
  
 L’exemple suivant montre une manière de réécrire votre code pour résoudre l’erreur C4503 :  
  
```  
// C4503b.cpp  
// compile with: /W1 /EHsc /c  
#include <string>  
#include <map>  
  
class Field{};  
struct Screen2 {  
   std::map<std::string, Field> Element;  
};  
  
struct WebApp2 {  
   std::map<std::string, Screen2> Element;  
};  
  
struct WebAppTest2 {  
   std::map<std::string, WebApp2> Element;  
};  
  
struct Hello2 {  
   std::map<std::string, WebAppTest2> Element;  
};  
  
Hello2 MyWAT2;  
```
