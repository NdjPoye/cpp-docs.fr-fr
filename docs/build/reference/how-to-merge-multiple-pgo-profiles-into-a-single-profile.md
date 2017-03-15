---
title: "Comment&#160;: fusionner plusieurs profils PGO en un seul profil | Microsoft Docs"
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
  - "fusionner les profils"
  - "optimisations guidées par profil, fusionner les profils"
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Comment&#160;: fusionner plusieurs profils PGO en un seul profil
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'optimisation guidée par profil \(PGO\) est un formidable outil pour créer des fichiers binaires optimisés à partir d'un scénario profilé.  Mais que se passe\-t\-il dans le cas d'une application ayant plusieurs scénarios importants mais distincts ? Comment créer, à partir de plusieurs scénarios différents, un profil unique utilisable par la PGO ?  Dans Visual Studio, PGO Manager \(Pgomgr.exe\) se charge de cette tâche.  
  
 Voici la syntaxe servant à fusionner des profils :  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 où `num` est une pondération facultative utilisée pour cette fusion.  Les pondérations sont couramment utilisées si certains scénarios sont plus importants que d'autres ou doivent être exécutés plusieurs fois.  
  
> [!NOTE]
>  Le PGO Manager ne fonctionnera pas avec des données de profil périmées.  Pour fusionner un fichier .pgc dans un fichier .pgd, le fichier .pgc doit être généré par un fichier exécutable créé par le même appel de lien que celui qui a généré le fichier .pgd.  
  
## Exemple  
 Dans cet exemple, le PGO Manager ajoutera six fois pgcFile.pgc à pgdFile.pgd.  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## Exemple  
 Dans cet exemple, le PGO Manager ajoutera pgcFile1.pgc et pgcFile2.pgc à pgdFile.pgd, deux fois pour chaque fichier .pgc.  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## Exemple  
 Si le PGO Manager est exécuté sans fichier .pgc, il recherchera dans le répertoire local tous les fichiers .pgc ayant le même nom que le fichier .pgd suivi d'un point d'exclamation \(\!\) puis de caractères arbitraires.  Si le répertoire local comporte des fichiers test.pgd, test\!1.pgc, test2.pgc et test\!hello.pgc, et si la commande suivante est exécutée à partir du répertoire local, alors test\!1.pgc et test\!hello.pgc seront fusionnés avec test.pgd.  
  
```  
pgomgr /merge test.pgd  
```  
  
## Voir aussi  
 [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md)