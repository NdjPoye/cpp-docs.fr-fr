---
title: "Flux de sortie | Microsoft Docs"
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
  - "flux de sortie"
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
caps.latest.revision: 12
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Flux de sortie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Objet du flux de sortie est une destination pour les octets.  Les trois classes les plus importantes du flux de sortie sont `ostream`, `ofstream`, et `ostringstream`.  
  
 La classe d'`ostream`, par la classe dérivée `basic_ostream`, prend en charge les objets de flux prédéfinis :  
  
-   sortie standard d'`cout`  
  
-   erreur standard d'`cerr`avec la mise en mémoire tampon limitée  
  
-   `clog` semblable à `cerr` mais avec la mise en mémoire tampon saturée  
  
 Les objets sont rarement construits à partir de `ostream`; les objets prédéfinis sont généralement utilisés.  Dans certains cas, vous pouvez réaffecter les objets prédéfinis après démarrage du programme.  La classe d'`ostream`, qui peut être configurée pour l'opération mise en mémoire tampon ou non tamponnée, le mieux adapté à la sortie séquentiel de mode texte.  Toutes les fonctionnalités de la classe de base, `ios`, est incluse dans `ostream`.  Si vous construisez un objet de la classe `ostream`, vous devez spécifier un objet d'`streambuf` au constructeur.  
  
 La classe d'`ofstream` prend en charge la sortie du fichier de disque.  Si vous avez besoin d'un disque réservé à l'OUTPUT, construisez un objet de la classe `ofstream`.  Vous pouvez spécifier si les objets d'`ofstream` reçoivent binary ou le mode de texte lors de la construction de l'objet d'`ofstream` ou en appelant la fonction membre d'`open` de l'objet.  De nombreuses options de mise en forme et de fonctions membres appliquent à `ofstream` des objets, et toutes les fonctionnalités des classes de base `ios` et `ostream` est incluse.  
  
 Si vous spécifiez un nom de fichier dans le constructeur, ce fichier est automatiquement ouvert lorsque l'objet est créé.  Sinon, vous pouvez utiliser la fonction membre d'`open` après avoir appelé le constructeur par défaut.  
  
 Comme la fonction\) `sprintf_s`, la classe d'`ostringstream` prend en charge la sortie des chaînes en mémoire.  Pour créer une chaîne de la mémoire à l'aide de le format de flux d'E\/S, construisez un objet de la classe `ostringstream`.  
  
## Dans cette section  
 [Construction d'objets de flux de sortie](../standard-library/constructing-output-stream-objects.md)  
  
 [Utilisation des opérateurs d'insertion et contrôle du format](../standard-library/using-insertion-operators-and-controlling-format.md)  
  
 [Fonctions membres de flux de fichiers de sortie](../standard-library/output-file-stream-member-functions.md)  
  
 [Effets de la mise en mémoire tampon](../standard-library/effects-of-buffering.md)  
  
 [Fichiers de sortie binaires](../standard-library/binary-output-files.md)  
  
 [Surcharge de l'opérateur \<\< pour vos propres classes](../standard-library/overloading-the-output-operator-for-your-own-classes.md)  
  
 [Écrire vos propres manipulateurs sans arguments](../standard-library/writing-your-own-manipulators-without-arguments.md)  
  
## Voir aussi  
 [\<ostream\> Members](http://msdn.microsoft.com/fr-fr/a5afd034-0e3c-41ee-bbd7-468d9188da1d)   
 [ofstream](../Topic/ofstream.md)   
 [ostringstream](../Topic/ostringstream.md)   
 [basic\_ostream Members](http://msdn.microsoft.com/fr-fr/82e5cc91-7c0c-4950-a8ce-ac779cfbbd93)   
 [iostream, programmation](../standard-library/iostream-programming.md)