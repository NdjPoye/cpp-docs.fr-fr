---
title: "E/S niveau bas | Microsoft Docs"
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
  - "c.io"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "handles de fichiers (C++)"
  - "handles de fichiers (C++), fonctions E/S"
  - "E/S (CRT), fonctions"
  - "E/S (CRT), niveau bas"
  - "routines E/S niveau bas"
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# E/S niveau bas
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces fonctions appellent le système d'exploitation directement à l'opération de niveau inférieur à celui fourni par les entrées\/sorties \(E\/S\) de flux de données.  Les appels de bas niveau d'entrée et de sortie ne mettent pas en mémoire tampon ni ne mettent en forme des données.  
  
 Les routines de bas niveau peuvent accéder aux flux de données standard ouverts au démarrage du programme à l'aide de les descripteurs de fichier prédéfinis suivants.  
  
|Stream|Descripteur du fichier|  
|------------|----------------------------|  
|`stdin`|0|  
|`stdout`|1|  
|`stderr`|2|  
  
 Les routines de bas niveau d'E\/S définissent la variable globale [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) lorsqu'une erreur se produit.  Vous devez inclure STDIO.H lorsque vous utilisez les fonctions de bas niveau uniquement si votre programme requiert une constante définie dans STDIO.H, tel que l'indicateur de fin de fichier \(`EOF`\).  
  
### Fonctions E\/S de bas niveau  
  
|Fonction|Utilisez|  
|--------------|--------------|  
|[\_close](../c-runtime-library/reference/close.md)|Close file|  
|[\_commit](../c-runtime-library/reference/commit.md)|Vide le fichier de disque|  
|[\_creat, \_wcreat](../c-runtime-library/reference/creat-wcreat.md)|Créez un fichier|  
|[\_dup](../c-runtime-library/reference/dup-dup2.md)|Retourne le descripteur de fichier disponible suivant pour un fichier donné|  
|[\_dup2](../c-runtime-library/reference/dup-dup2.md)|Créez le deuxième descripteur du fichier donné|  
|[\_eof](../c-runtime-library/reference/eof.md)|Test pour la fin de fichier|  
|[\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Replacez le pointeur de fichier à l'emplacement spécifié|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|Ouvrir un fichier|  
|[\_read](../c-runtime-library/reference/read.md)|Lire des données dans un fichier|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Ouvrir le fichier pour le partager|  
|[\_tell, \_telli64](../c-runtime-library/reference/tell-telli64.md)|Obtient la position actuelle du pointeur de fichier|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../c-runtime-library/reference/umask-s.md)|Définissez le masque d'autorisation de fichier|  
|[\_write](../c-runtime-library/reference/write.md)|Ecrire des données à classer|  
  
 `_dup` et `_dup2` sont généralement utilisés pour associer les descripteurs de fichier prédéfinis à des fichiers différents.  
  
## Voir aussi  
 [Entrées et sorties](../c-runtime-library/input-and-output.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Appels système](../c-runtime-library/system-calls.md)