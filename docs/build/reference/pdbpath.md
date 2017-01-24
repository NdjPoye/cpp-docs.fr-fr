---
title: "/PDBPATH | Microsoft Docs"
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
  - "/pdbpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pdb, chemin"
  - "/PDBPATH (option Dumpbin)"
  - "fichiers PDB, chemin"
  - "PDBPATH (option Dumpbin)"
  - "-PDBPATH (option Dumpbin)"
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDBPATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBPATH[:VERBOSE] filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 Nom du fichier .dll ou .exe dont vous voulez trouver le fichier .pdb correspondant.  
  
 VERBOSE \(facultatif\)  
 Indique tous les répertoires ayant fait l'objet d'une recherche du fichier .pdb.  
  
## Notes  
 \/PDBPATH parcourt l'ordinateur en suivant les mêmes chemins que ceux qui ont été empruntés par le débogueur pour rechercher un fichier .pdb et indique, le cas échéant, les fichiers .pdb correspondants au fichier spécifié dans *filename*.  
  
 Lorsque vous utilisez le débogueur Visual Studio, vous pouvez rencontrer un problème lié au fait que le débogueur utilise un fichier .pdb dont la version est différente du fichier que vous déboguez.  
  
 \/PDBPATH recherchera les fichiers .pdb en utilisant les chemins suivants :  
  
-   Vérification de l'emplacement où réside l'exécutable.  
  
-   Vérification de l'emplacement du PDB écrit dans l'exécutable.  Il s'agit en fait de l'emplacement au moment où l'image a été liée.  
  
-   Vérification selon le chemin de recherche configuré dans l'IDE de Visual Studio.  
  
-   Vérification selon les chemins qui figurent dans les variables d'environnement \_NT\_SYMBOL\_PATH et \_NT\_ALT\_SYMBOL\_PATH.  
  
-   Vérification dans le répertoire Windows.  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)   
 [\/PDBALTPATH \(Utiliser un autre chemin d'accès PDB\)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)