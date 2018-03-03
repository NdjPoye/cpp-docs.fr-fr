---
title: Compilateur avertissement (niveau 1) C4503 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f8af13ffdcd71d760a180340a79a863cecb5e32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4503"></a>Avertissement du compilateur (niveau 1) C4503
'identificateur' : nom longueur décoré dépassée, nom a été tronqué.  
  
 Le nom décoré a dépassé la limite du compilateur (4096) et a été tronqué. Pour éviter cet avertissement et la troncature, réduisez le nombre d’arguments ou la longueur du nom des identificateurs utilisés.  
  
 Une situation où cet avertissement est émis est lorsque votre code contient des modèles spécialisés à plusieurs reprises sur des modèles.  Par exemple, une table de tables (à partir de la bibliothèque C++ Standard).  Dans ce cas, vous pouvez apporter à vos typedefs un type (struct, par exemple) qui contient le mappage.  
  
 Vous pouvez, toutefois, décider de ne pas restructurer votre code.  Il est possible d’envoyer une application qui génère l’erreur C4503, mais si vous obtenez des erreurs au moment de lien sur un symbole tronqué, il sera plus difficile de déterminer le type du symbole dans l’erreur.  Le débogage sera également plus difficile ; le débogueur disposera de mappage, il est difficile de nom de symbole pour le nom de type.  Toutefois, l’exactitude du programme, n’est pas affectée par le nom tronqué.  
  
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
  
 L’exemple suivant montre une façon de réécrire votre code pour résoudre l’erreur C4503 :  
  
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