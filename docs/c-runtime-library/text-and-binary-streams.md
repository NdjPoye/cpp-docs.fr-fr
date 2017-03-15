---
title: "Flux texte et binaires | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flux binaires"
  - "flux de texte"
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Flux texte et binaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un flux de texte consiste en une ou plusieurs lignes de texte qui peuvent être écrites sur un support adapté au texte afin qu'elles puissent être lues.  Lors de la lecture d'un flux de texte, le programme lit un `NL` \(saut de ligne\) à la fin de chaque ligne.  Lors de l'écriture sur un flux de texte, le programme écrit `NL` pour signaler la fin d'une ligne.  Pour faire correspondre les conventions différentes dans les environnements cibles pour représenter le texte dans les fichiers, les fonctions de la bibliothèque peuvent modifier le nombre et les représentations de caractères transmis entre le programme et un flux de texte.  
  
 Par conséquent, le positionnement dans un flux de texte est limité.  Vous pouvez obtenir l'indicateur d'emplacement de fichier actuel en appelant [fgetpos](../c-runtime-library/reference/fgetpos.md) ou [ftell](../c-runtime-library/reference/ftell-ftelli64.md).  Vous pouvez positionner un flux de texte dans une position obtenue de cette façon, ou au début ou à la fin du flux de données, en appelant [fsetpos](../c-runtime-library/reference/fsetpos.md) ou [fseek](../c-runtime-library/reference/fseek-fseeki64.md).  Toute autre modification de l'emplacement peut ne pas être bien prise en charge.  
  
 Pour une portabilité maximale, le programme ne doit pas écrire :  
  
-   Fichiers vides.  
  
-   Les espaces à la fin d'une ligne.  
  
-   Lignes partielles \(en omettant `NL` à la fin d'un fichier\).  
  
-   caractères autres que des caractères imprimables, NL, et `HT` \(tabulation horizontale\).  
  
 Si vous suivez ces règles, la séquence de caractères que vous lisez à partir d'un flux de texte \(comme octets ou comme caractères multioctets\) correspondra à la séquence de caractères que vous avez entrée au flux de texte lors de la création du fichier.  Sinon, les fonctions de la bibliothèque peuvent supprimer un fichier que vous avez créé si le fichier est vide lorsque vous le fermez.  Ou ils peuvent modifier ou supprimer les caractères que vous entrez dans le fichier.  
  
 Un flux binaire se compose d'un ou de plusieurs octets d' informations aléatoires.  Vous pouvez écrire la valeur stockée dans un objet aléatoire comme un flux binaire \(niveau octets\) et lire exactement ce qui a été enregistré dans l'objet lorsque vous l'avez entré.  Les fonctions de la bibliothèque n'altèrent pas les octets que vous transmettez entre l'application et un flux binaire.  Ils peuvent, toutefois, ajouter un nombre aléatoire d'octets NULL dans le fichier que vous entrez dans un flux binaire.  Le programme doit traiter ces octets NULL supplémentaires à la fin de tous les flux binaires.  
  
 Par conséquent, le positionnement dans un flux binaire est bien défini, à l'exception du positionnement relatif à la fin du flux de données.  Vous pouvez obtenir et modifier l'indicateur d'emplacement de fichier actuel de la même manière que pour un flux de texte.  De plus, les décalages utilisés par [ftell](../c-runtime-library/reference/ftell-ftelli64.md) et [fseek](../c-runtime-library/reference/fseek-fseeki64.md) comptent les octets depuis le début du flux \(qui est l'octet zéro\), l'arithmétique entière sur les décalages génère des résultats prévisibles.  
  
 Un flux d'octets traite un fichier comme séquence d'octets.  Dans le cadre du programme, le flux ressemble à la même séquence d'octets, à l'exception des modifications possibles décrites ci\-dessus.  
  
## Voir aussi  
 [Fichiers et flux](../c-runtime-library/files-and-streams.md)