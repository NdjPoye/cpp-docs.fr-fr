---
title: "Flux d&#39;entr&#233;e/sortie | Microsoft Docs"
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
  - "E/S (C++), flux de données"
  - "E/S de flux"
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Flux d&#39;entr&#233;e/sortie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`basic_iostream`, défini dans le fichier d'en\-tête \<istream\>, est le modèle de la classe pour les objets qui gèrent les deux flux d'E\/S basés caractérisé en entrée et sortie.  
  
 Il existe deux typedefs qui définissent des spécialisations de caractères spécifique à `basic_iostream` et peuvent aider à simplifier le code pour lire : `iostream` \(ne pas être confondu avec le fichier d'en\-tête \<iostream\>\) est un flux d'E\/S basé sur `basic_iostream<char>`; `wiostream` est un flux d'E\/S basé sur `basic_iostream<wchar_t>`.  
  
 Pour plus d'informations, consultez [basic\_iostream, classe](../standard-library/basic-iostream-class.md), [iostream](../Topic/iostream.md) et [wiostream](../Topic/wiostream.md).  
  
 Dérivant de `basic_iostream`, le modèle de la classe `basic_fstream` est utilisé pour transmettre en continu des données caractères vers et à partir de fichiers.  
  
 Il existe également des typedefs qui fournissent des spécialisations de caractères spécifique à `basic_fstream`.  Elles sont `fstream`, un flux d'E\/S de fichier qui est basé sur `char`, et `wfstream`, un flux d'E\/S de fichier qui est basé sur `wchar_t`.  Pour plus d'informations, consultez [basic\_fstream, classe](../standard-library/basic-fstream-class.md), [fstream](../Topic/fstream.md) et [wfstream](../Topic/wfstream.md).  Ces typedefs requiert l'inclusion du fichier d'en\-tête \<fstream\>.  
  
> [!NOTE]
>  Lorsqu'un objet `basic_fstream` est utilisé pour effectuer les E\/S d'un fichier, même si la mémoire tampon sous\-jacente contient les positions désignées séparément pour la lecture et pour l'écriture, les positions actuelles d'entrée et de sortie sont liées ensemble ; par conséquent, la lecture de certaines données déplace la position de sortie.  
  
 Le modèle de la classe `basic_stringstream` et la spécialisation commune, `stringstream`, sont souvent utilisés pour traiter les objets de flux d'E\/S pour insérer et extraire des données de caractères.  Pour plus d'informations, consultez [basic\_stringstream, classe](../standard-library/basic-stringstream-class.md).  
  
## Voir aussi  
 [stringstream](../Topic/stringstream.md)   
 [basic\_stringstream, classe](../standard-library/basic-stringstream-class.md)   
 [\<sstream\>](../standard-library/sstream.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)