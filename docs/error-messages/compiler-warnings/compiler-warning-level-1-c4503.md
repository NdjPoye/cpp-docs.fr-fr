---
title: "Avertissement du compilateur (niveau 1) C4503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4503"
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : longueur du nom décoré dépassée, le nom a été tronqué  
  
 Le nom décoré était plus long que la limite du compilateur \(4096\), il a été tronqué.  Pour éviter cet avertissement et la troncature, réduisez le nombre d'arguments ou la longueur du nom des identificateurs utilisés.  
  
 Cet avertissement peut notamment être émis si votre code contient des modèles spécialisés à plusieurs reprises sur des modèles.  Par exemple, une table de tables \(de la bibliothèque C\+\+ standard\).  Dans ce cas, vous pouvez affecter à vos typedefs un type \(struct, par exemple\) qui contient la table.  
  
 Toutefois, vous pouvez décider de ne pas restructurer votre code.  Il est possible d'expédier une application qui génère l'erreur C4503, mais si vous rencontrez des erreurs au moment de la liaison sur un symbole tronqué, il sera plus difficile de déterminer le type du symbole dans l'erreur.  Le débogage sera également plus compliqué, car le débogueur rencontrera également des difficultés lors du mappage du nom du symbole au nom du type.  Toutefois, l'exactitude du programme n'est pas affectée par le nom tronqué.  
  
 L'exemple suivant génère l'erreur C4503 :  
  
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
  
 L'exemple suivant illustre une manière de réécrire votre code pour résoudre l'erreur C4503 :  
  
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