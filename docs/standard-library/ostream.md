---
title: "&lt;ostream&gt; | Microsoft Docs"
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
  - "std.<ostream>"
  - "<ostream>"
  - "ostream/std::<ostream>"
  - "std::<ostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream (en-tête)"
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: 20
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de modèle [basic\_ostream](../standard-library/basic-ostream-class.md), qui sert d'intermédiaire pour les insertions des iostreams.  L'en\-tête définit également plusieurs manipulateurs associés.  Cet en\-tête est généralement inclus pour vous par l'un des autres en\-tête iostream.  Vous devez rarement l'inclure directement.\)  
  
## Syntaxe  
  
```  
  
#include <ostream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[ostream](../Topic/ostream.md)|Crée un type à partir de `basic_ostream` qui est spécialisé sur `char` et `char_traits` spécialisé sur `char`.|  
|[wostream](../Topic/wostream.md)|Crée un type à partir de `basic_ostream` qui est spécialisé sur `wchar_t` et `char_traits` spécialisé sur `wchar_t`.|  
  
### Manipulateurs  
  
|||  
|-|-|  
|[endl](../Topic/endl.md)|Met fin à une ligne et vide la mémoire tampon.|  
|[ends](../Topic/ends%20\(Standard%20C++%20Library\).md)|Met fin à une chaîne.|  
|[flush](../Topic/flush%20\(Standard%20C++%20Library\).md)|Vide la mémoire tampon.|  
||Échange les valeurs du paramètre d'objet `basic_ostream` de gauche avec celles du paramètre d'objet `basic_ostream` de droite.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\<\<](../Topic/operator%3C%3C%20\(%3Costream%3E\).md)|Écrit différents types dans le flux.|  
  
### Classes  
  
|||  
|-|-|  
|[basic\_ostream](../standard-library/basic-ostream-class.md)|La classe de modèle décrit un objet qui contrôle l'insertion d'éléments et d'objets encodés dans une mémoire tampon de flux.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)