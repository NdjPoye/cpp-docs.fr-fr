---
title: "Flux d&#39;entr&#233;e | Microsoft Docs"
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
  - "données (C++), lire à partir d'un flux d'entrée"
  - "objets de flux d'entrée"
  - "flux d'entrée"
  - "lire des données (C++), à partir de flux d'entrée"
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Flux d&#39;entr&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un objet de flux d'entrée est une source d'octets.  Les trois classes les plus importantes de flux d'entrée sont [istream](http://msdn.microsoft.com/fr-fr/6801779e-260e-416d-b4ec-fef5ff1b2371), [ifstream](../Topic/ifstream.md), et [istringstream](../Topic/istringstream.md).  
  
 La classe d'`istream` convient d'entrée séquentiel de mode texte.  Vous pouvez configurer des objets de classe `istream` pour l'opération mise en mémoire tampon ou non tamponnée.  Toutes les fonctionnalités de la classe de base, `ios`, est incluse dans `istream`.  Vous construirez rarement des objets de classe `istream`.  À la place, vous utiliserez généralement l'objet prédéfini d'`cin`, qui est en fait un objet de la classe [ostream](../standard-library/ostream.md).  Dans certains cas, vous pouvez affecter `cin` à d'autres objets de flux après démarrage du programme.  
  
 La classe d'`ifstream` prend en charge l'entrée de fichier disque.  Si vous avez besoin d'un fichier de disque réservé à l'entrée, construisez un objet de la classe `ifstream`.  Vous pouvez spécifier le format binaire ou le mode de texte.  Si vous spécifiez un nom de fichier dans le constructeur, ce fichier est automatiquement ouvert lorsque l'objet est créé.  Sinon, vous pouvez utiliser la fonction d'`open` après avoir appelé le constructeur par défaut.  De nombreuses options de mise en forme et de fonctions membres appliquent à `ifstream` des objets.  Toutes les fonctionnalités des classes de base `ios` et `istream` est incluse dans `ifstream`.  
  
 Comme la fonction de bibliothèque `sscanf_s`, la classe d'`istringstream` prend en charge l'entrée des chaînes en mémoire.  Pour extraire des données d'un tableau de caractères avec une marque de fin null, allouez et initialiser la chaîne, puis construire un objet de la classe `istringstream`.  
  
## Dans cette section  
 [Construction d'objets de flux d'entrée](../standard-library/constructing-input-stream-objects.md)  
  
 [Utilisation d'opérateurs d'extraction](../standard-library/using-extraction-operators.md)  
  
 [Tester les erreurs d'extraction](../standard-library/testing-for-extraction-errors.md)  
  
 [Manipulateurs de flux d'entrée](../standard-library/input-stream-manipulators.md)  
  
 [Fonctions membres de flux de fichiers d'entrée](../standard-library/input-stream-member-functions.md)  
  
 [Surcharge de l'opérateur \>\> pour vos propres classes](../standard-library/overloading-the-input-operator-for-your-own-classes.md)  
  
## Voir aussi  
 [iostream, programmation](../standard-library/iostream-programming.md)