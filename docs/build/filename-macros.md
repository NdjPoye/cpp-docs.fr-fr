---
title: "Macros de noms de fichiers | Microsoft Docs"
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
  - "macros de noms de fichiers dans NMAKE"
  - "macros, NMAKE"
  - "programme NMAKE, macros de noms de fichiers"
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Macros de noms de fichiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les macros de noms de fichiers sont prédéfinies en tant que noms de fichiers spécifiés dans la dépendance \(il ne s'agit pas de spécifications de noms de fichiers complètes sur le disque\).  Il n'est pas nécessaire de mettre ces macros entre parenthèses pour les appeler ; il suffit de spécifier un $ comme indiqué.  
  
|Macro|Signification|  
|-----------|-------------------|  
|**$@**|Nom complet de la cible en cours \(chemin d'accès, nom de base, extension\), telle qu'elle est définie.|  
|**$$@**|Nom complet de la cible en cours \(chemin d'accès, nom de base, extension\), telle qu'elle est définie.  Valable uniquement en tant que dépendant dans une dépendance.|  
|**$\***|Chemin d'accès et nom de base de la cible en cours moins l'extension de fichier.|  
|**$\*\***|Tous les dépendants de la cible en cours.|  
|**$?**|Tous les dépendants dotés d'un horodatage postérieur à celui de la cible en cours.|  
|**$\<**|Fichier dépendant avec un horodatage postérieur à celui de la cible en cours.  Valable uniquement dans les commandes utilisées dans les fichiers d'inférence.|  
  
 Pour spécifier une partie d'une macro de nom de fichier prédéfinie, ajoutez un modificateur de macro et placez la macro modifiée entre parenthèses.  
  
|Modificateur|Partie de nom de fichier obtenue|  
|------------------|--------------------------------------|  
|**J**|Lecteur plus répertoire|  
|**B**|Nom de base|  
|**F**|Nom de base plus extension|  
|**R**|Lecteur plus répertoire plus nom de base|  
  
## Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)