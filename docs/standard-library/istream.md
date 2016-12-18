---
title: "&lt; istream &gt; | Microsoft Docs"
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
  - "istream/std::<istream>"
  - "std.<istream>"
  - "<istream>"
  - "std::<istream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream (en-tête)"
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
caps.latest.revision: 20
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; istream &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de modèle basic\_istream, qui sert d'intermédiaire pour l'extraction des iostreams, et la classe de modèle basic\_iostream, qui sert d'intermédiaire pour les insertions et les extractions. L'en\-tête définit également un manipulateur associé. Ce fichier d'en\-tête est généralement inclus pour vous par un autre en\-tête iostreams ; vous devez rarement l'inclure directement.  
  
## Syntaxe  
  
```  
  
#include <istream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[iostream](../Topic/iostream.md)|Type `basic_iostream` spécialisé sur `char`.|  
|[istream](../Topic/istream.md)|Type `basic_istream` spécialisé sur `char`.|  
|[wiostream](../Topic/wiostream.md)|Type `basic_iostream` spécialisé sur **wchar**.|  
|[wistream](../Topic/wistream.md)|Type `basic_istream` spécialisé sur **wchar**.|  
  
### Manipulateurs  
  
|||  
|-|-|  
|[ws](../Topic/ws.md)|Ignore l'espace blanc dans le flux.|  
|[swap](../Topic/%3Cistream%3E%20swap.md)|Échange deux objets de flux.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[\>\>, opérateur](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md)|Extrait des chaînes et des caractères à partir du flux.|  
  
### Classes  
  
|||  
|-|-|  
|[basic\_iostream](../standard-library/basic-iostream-class.md)|Classe de flux qui peut effectuer à la fois l'entrée et la sortie.|  
|[basic\_istream](../standard-library/basic-istream-class.md)|La classe de modèle décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux avec des éléments de type **Elem**, également appelé [char\_type](../Topic/basic_ios::char_type.md), dont les caractéristiques sont déterminées par la classe **Tr**, également appelée [traits\_type](../Topic/basic_ios::traits_type.md).|  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)