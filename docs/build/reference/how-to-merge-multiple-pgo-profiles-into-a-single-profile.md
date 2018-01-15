---
title: "Comment : fusionner plusieurs profils PGO en un seul profil | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 880e9fbba7852a9a7919e73f80b73e34394cd037
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Comment : fusionner plusieurs profils PGO en un seul profil
L’optimisation guidée par profil (PGO) est un excellent outil pour la création des fichiers binaires optimisés basées sur un scénario de profilage. Mais que se passe-t-il si vous disposez d’une application qui a plusieurs scénarios importants, mais distinctes. comment créer un profil unique que PGO peut utiliser à partir de différents scénarios ? Dans Visual Studio, PGO Manager, Pgomgr.exe effectue cette tâche pour vous.  
  
 La syntaxe pour fusionner les profils est :  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 où `num` est une pondération facultative qui est utilisée pour cette fusion. Poids sont couramment utilisées si certains scénarios sont plus importants que d’autres personnes ou s’il existe des scénarios qui doivent être exécutées plusieurs fois.  
  
> [!NOTE]
>  Le Gestionnaire de PGO ne fonctionnera pas avec les données de profil périmées. Pour fusionner un fichier .pgc dans un fichier .pgd, le fichier .pgc doit être généré par un fichier exécutable qui a été créé par le même appel de lien qui a généré le fichier .pgd.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, le PGO Manager ajoutera pgcFile.pgc à pgdFile.pgd six fois.  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, le PGO Manager ajoutera pgcFile1.pgc et pgcFile2.pgc à pgdFile.pgd, deux fois pour chaque fichier .pgc.  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Exemple  
 Si le PGO Manager est exécuté sans fichier .pgc, il recherche le répertoire local pour tous les fichiers .pgc qui ont le même nom que le fichier .pgd avec un point d’exclamation ( !) suivies de caractères arbitraires. Si le répertoire local a test, test ! 1.pgc, test2.pgc et fichiers test.pgd, et la commande suivante est exécutée à partir du répertoire local, test ! 1.pgc et test sont fusionnées test.pgd.  
  
```  
pgomgr /merge test.pgd  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md)