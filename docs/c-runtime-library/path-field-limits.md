---
title: "Limites de champ de chemin | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_MAX_EXT"
  - "_MAX_DIR"
  - "_MAX_PATH"
  - "_MAX_FNAME"
  - "_MAX_DRIVE"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_MAX_DIR (constante)"
  - "_MAX_DRIVE (constante)"
  - "_MAX_EXT (constante)"
  - "_MAX_FNAME (constante)"
  - "_MAX_PATH (constante)"
  - "MAX_DIR (constante)"
  - "MAX_DRIVE (constante)"
  - "MAX_EXT (constante)"
  - "MAX_FNAME (constante)"
  - "constantes de champ de chemin d'accès"
  - "chemins d'accès, limite maximale"
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Limites de champ de chemin
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
#include <stdlib.h>  
```  
  
## Notes  
 Ces constantes définissent les longueurs maximales du chemin d'accès et des champs individuels dans le chemin d'accès.  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_MAX_DIR`|Longueur maximale du chemin d'accès du composant.|  
|`_MAX_DRIVE`|Longueur maximale de composant de lecteur|  
|`_MAX_EXT`|Longueur maximale des composants d'extension|  
|`_MAX_FNAME`|Longueur maximale des composants nom de fichier|  
|`_MAX_PATH`|Longueur maximale de chemin d'accès complet|  
  
> [!NOTE]
>  Le temps de parcours en C prend en charge des longueurs de trajet jusqu'à 32768 caractères de longueur, mais il appartient au système d'exploitation, notamment au système de fichiers, pour prendre en charge les chemins d'accès plus longs.  La somme des champs ne doit pas dépasser `_MAX_PATH` pour la compatibilité descendante complète avec des systèmes de fichiers FAT32.  [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../c-runtime-library/includes/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], et chemins de supports du système de fichiers Windows Vista NTFS jusqu'à 32768 caractères de longueur, mais uniquement en utilisant les API Unicode.  Lors de l'utilisation de long noms de chemin d'accès, préfixez le chemin d'accès aux dossiers avec les caractères \\\\?\\ et utilisez les versions Unicode des fonctions C Runtime.  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)