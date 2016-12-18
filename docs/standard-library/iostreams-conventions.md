---
title: "iostreams, conventions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iostream (en-tête)"
  - "bibliothèque C++ standard, iostreams"
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iostreams, conventions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les en\-têtes d'iostreams prennent en charge les conversions entre le texte et les formes encodés, et l'entrée et la sortie des fichiers externes :  
  
|||  
|-|-|  
|[\<fstream\>](../standard-library/fstream.md)|[\< iomanip \>](../standard-library/iomanip.md)|  
|[\<ios\>](../standard-library/ios.md)|[\<iosfwd\>](../standard-library/iosfwd.md)|  
|[\<iostream\>](../standard-library/iostream.md)|[\< istream \>](../standard-library/istream.md)|  
|[\<ostream\>](../standard-library/ostream.md)|[\<sstream\>](../standard-library/sstream.md)|  
|[\< streambuf \>](../standard-library/streambuf.md)|[\<strstream\>](../standard-library/strstream.md)|  
  
 L'utilisation la plus simple de iostreams requiert uniquement si vous incluez l'en\-tête [\<iostream\>](../standard-library/iostream.md).  Vous pouvez ensuite extraire les valeurs d'[cin](../Topic/cin.md) ou de [wcin](../Topic/wcin.md) pour lire l'entrée standard.  Les règles pour cela sont présentées dans la description de la classe [basic\_istream, classe](../standard-library/basic-istream-class.md).  Vous pouvez également insérer des valeurs à [cout](../Topic/cout.md) ou à [wcout](../Topic/wcout.md) écrire la sortie standard.  Les règles pour cela sont présentées dans la description de la classe [basic\_ostream, classe](../standard-library/basic-ostream-class.md).  Le courantes de format à deux extracteurs et insertors est gérée par la classe [basic\_ios, classe](../standard-library/basic-ios-class.md).  Manipuler ces informations de format sous le couvert d'extraire et d'insérer des objets est la province plusieurs manipulateurs.  
  
 Vous pouvez effectuer les mêmes opérations d'iostreams sur les fichiers que vous ouvrirez de nom, à l'aide de les classes déclarées dans [\<fstream\>](../standard-library/fstream.md).  Pour convertir les iostreams et les objets de la classe [basic\_string, classe](../standard-library/basic-string-class.md), utilisez les classes déclarées dans [\<sstream\>](../standard-library/sstream.md).  Pour effectuer la même des chaînes de l'Assistant De c, utilisez les classes déclarées dans [\<strstream\>](../standard-library/strstream.md).  
  
 Les en\-têtes autres fournissent des services de support technique, classique d'intérêt direct aux la plupart des utilisateurs expérimentés des classes d'iostreams.  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)