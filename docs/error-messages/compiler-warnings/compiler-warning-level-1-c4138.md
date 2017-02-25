---
title: "Avertissement du compilateur (niveau&#160;1) C4138 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4138"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4138"
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4138
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\*\/' trouvé à l'extérieur du commentaire  
  
 Le délimiteur de commentaire de clôture n’est pas précédé d’un délimiteur de commentaire d’ouverture. Le compilateur suppose l’existence d’un espace entre l’astérisque \(**\***\) et la barre oblique \(\/\).  
  
## Exemple  
  
```  
// C4138a.cpp // compile with: /W1 int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning int main() { }  
```  
  
 Cet avertissement peut être provoqué par une tentative d’imbrication de commentaires.  
  
 Cet avertissement peut être résolu en plaçant en commentaire des sections de code contenant elles\-mêmes des commentaires, en incluant le code dans un bloc **\#if\/\#endif** et en définissant une valeur zéro pour l’expression de contrôle :  
  
```  
// C4138b.cpp // compile with: /W1 #if 0 int my_variable;   /* Declaration currently not needed */ #endif int main() { }  
```