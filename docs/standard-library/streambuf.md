---
title: "&lt; streambuf &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<streambuf>"
  - "<streambuf>"
  - "streambuf/std::<streambuf>"
  - "std.<streambuf>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "streambuf (en-tête)"
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; streambuf &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez l'en\-tête standard iostreams \<streambuf\> pour définir la classe de modèle [basic\_streambuf](../standard-library/basic-streambuf-class.md), qui est essentielle au fonctionnement des classes iostreams. Cet en\-tête est généralement inclus pour vous par l'un des autres en\-tête iostream ; vous devez rarement l'inclure directement.  
  
## Syntaxe  
  
```  
  
#include <streambuf>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[streambuf](../Topic/streambuf.md)|Spécialisation de `basic_streambuf` qui utilise `char` comme paramètres du modèle.|  
|[wstreambuf](../Topic/wstreambuf.md)|Spécialisation de `basic_streambuf` qui utilise `wchar_t` comme paramètres du modèle.|  
  
### Classes  
  
|||  
|-|-|  
|[basic\_streambuf, classe](http://msdn.microsoft.com/fr-fr/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|La classe de modèle décrit une classe de base abstraite pour dériver une mémoire tampon de flux qui contrôle la transmission des éléments depuis et vers une représentation spécifique d'un flux.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)