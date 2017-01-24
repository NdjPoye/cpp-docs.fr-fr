---
title: "Utilisation des en-t&#234;tes de biblioth&#232;que C++ | Microsoft Docs"
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
  - "en-têtes"
  - "en-têtes, attribution des noms en C++ Directive Include"
  - "en-têtes, bibliothèque C++ standard"
  - "INCLUDE (directive)"
  - "en-têtes de bibliothèque"
  - "bibliothèque C++ standard, en-têtes"
  - "en-tête standard en C++"
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Utilisation des en-t&#234;tes de biblioth&#232;que C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous incluez le contenu d'un en\-tête standard en le nom d'une directive inclure.  
  
```  
#include <iostream>   // include I/O facilities  
```  
  
 Vous pouvez inclure des en\-têtes standard dans n'importe quel ordre, un en\-tête standard plusieurs fois, ou deux en\-têtes standard ou plus qui définissent la même macro ou la même type.  N'incluez pas d'en\-tête standard dans une déclaration.  Ne définissez pas les macros qui ont les mêmes noms que les mots clés avant d'inclure un en\-tête standard.  
  
 L'en\-tête de la bibliothèque actuelle c \+\+ inclut tous les autres en\-têtes de bibliothèque C\+\+ qu'il doit définir des types nécessaires. \(Inclut toujours explicitement tous les en\-têtes de bibliothèque C\+\+ nécessaires dans une unité de traduction, toutefois, de peur que vous deviniez le problème sur ses dépendances telles.\) Un en\-tête standard c De c ne sont jamais un autre en\-tête standard.  Un en\-tête standard déclare ou définit uniquement les entités décrites pour ce compte dans ce document.  
  
 Chaque fonction dans la bibliothèque est déclarée dans un en\-tête standard.  Contrairement à L'aide De c standard, l'en\-tête standard n'est jamais à une macro masquante le même nom que la fonction qui masque la déclaration de fonction et permet d'obtenir le même résultat.  Pour plus d'informations sur le masquage des macros, consultez [Conventions de la bibliothèque C\+\+](../standard-library/cpp-library-conventions.md).  
  
 Tous les noms en dehors de `operator delete` et `operator new` dans les en\-têtes de bibliothèque C\+\+ sont définis dans l'espace de noms d'`std`, ou dans un espace de noms imbriqué dans l'espace de noms d'`std`.  Vous faites référence au nom `cin`, par exemple, comme `std::cin`.  La notez, toutefois, que les noms de macros ne sont pas soumis à la qualification de l'espace de noms, vous entrez toujours `__STD_COMPLEX` sans qualificateur d'espace de noms.  
  
 Dans certains environnements de traduction, y compris l'en\-tête de la bibliothèque actuelle c \+\+ peut lever des noms externes déclaré également s dans l'espace de noms de `std` dans l'espace de noms global, avec des déclarations d'`using` pour chacune des étiquettes.  Sinon, l'en\-tête ne présente aucun nom de la bibliothèque dans l'espace de noms.  
  
 La norme C\+\+ les requiert que les en\-têtes standard c De c déclarent toutes les étiquettes externes dans l'espace de noms `std`, puis génère dans l'espace de noms global avec des déclarations d'`using` pour chacune des étiquettes.  Mais dans certains environnements de traduction les en\-têtes standard c De c n'incluent pas de déclaration d'espace de noms, indiquant les étiquettes directement dans l'espace de noms global.  Par conséquent, la méthode la plus portable de traiter les espaces de noms consiste à suivre les règles suivantes :  
  
-   Pour déclarer assurément dans l'espace de noms `std` un nom externe qui est traditionnellement déclaré dans \<stdlib.h, par\>exemple, incluez le cstdlib d'en\-tête \<.\>  Sachez que le nom peut également être déclarée dans l'espace de noms global.  
  
-   Pour déclarer assurément dans l'espace de noms global un nom externe déclaré dans \<stdlib.h, incluez\>l'en\-tête stdlib.h \<directement\>.  Sachez que le nom peut également être déclarée dans l'espace de noms `std`.  
  
 Par conséquent, si vous souhaitez appeler `std::abort` pour générer la arrêt anormal, vous devez inclure \<le cstdlib\>.  Si vous souhaitez appeler `abort`, vous devez inclure \<stdlib.h.\>  
  
 Ou bien, vous pouvez entrer la déclaration :  
  
```  
using namespace std;  
```  
  
 ce qui présente tous les noms de la bibliothèque dans l'espace de noms.  Si vous entrez des directives inclure de cette instruction immédiatement après que vous, levez les noms dans l'espace de noms global.  Vous pouvez ensuite ignorer les considérations relatives à l'espace de noms dans le reste de l'unité de traduction.  Pour éviter que la plupart des différences entre différents environnements de traduction.  
  
 À moins que spécifiquement indiqué sinon, vous ne pouvez pas définir des noms dans l'espace de noms d'`std`, ou dans un espace de noms imbriqué dans l'espace de noms d'`std`, dans le cadre de votre programme.  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)