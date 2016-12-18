---
title: "/PDBALTPATH (Utiliser un autre chemin d&#39;acc&#232;s PDB) | Microsoft Docs"
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
  - "/pdbaltpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pdb, chemin"
  - "/PDBALTPATH (option Dumpbin)"
  - "fichiers PDB, chemin"
  - "PDBALTPATH (option Dumpbin)"
  - "-PDBALTPATH (option Dumpbin)"
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDBALTPATH (Utiliser un autre chemin d&#39;acc&#232;s PDB)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBALTPATH:pdb_file_name  
```  
  
## Notes  
 où :  
  
 *pdb\_file\_name*  
 Chemin d'accès et nom de fichier du fichier .pdb.  
  
## Notes  
 Utilisez cette option pour fournir un autre emplacement pour le fichier de base de données de programme \(.pdb\) dans un fichier binaire compilé.  Normalement, l'éditeur de liens enregistre l'emplacement du fichier .pdb dans les binaires qu'il produit.  Vous pouvez utiliser cette option pour fournir un chemin d'accès et un nom de fichier différents pour le fichier .pdb.  Les informations fournies avec \/PDBALTPATH ne modifient pas l'emplacement ni le nom du fichier .pdb réel. Elles modifient les informations que l'éditeur de liens écrit dans le fichier binaire.  Cela vous permet de fournir un chemin d'accès indépendant de la structure de fichiers de l'ordinateur de build.  Cette option a deux applications courantes : fournir un chemin d'accès réseau et fournir un fichier sans informations de chemin d'accès.  
  
 La valeur de *pdb\_file\_name* peut être une chaîne arbitraire, une variable d'environnement ou **%\_PDB%**.  L'éditeur de liens développera une variable d'environnement, telle que **%SystemRoot%**, jusqu'à sa valeur.  L'éditeur de liens définit les variables d'environnement **%\_PDB%** et **%\_EXT%**.  La variable **%\_PDB%** est développée jusqu'au nom de fichier du fichier .pdb réel sans aucune information de chemin d'accès et la variable **%\_EXT%** est l'extension de l'exécutable généré.  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)   
 [\/PDBPATH](../../build/reference/pdbpath.md)