---
title: Macros de nom de fichier | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2073e4fcb365b3beb10d4040c0f54d9f61a0431
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="filename-macros"></a>Macros de noms de fichiers
Macros de nom de fichier sont prédéfinies en tant que noms de fichiers spécifiés dans la dépendance (nom de fichier complet pas les spécifications sur le disque). Ces macros n’avez pas besoin d’être mis entre parenthèses lorsqu’elle est appelée ; Spécifiez uniquement un $ comme indiqué.  
  
|Macro|Signification|  
|-----------|-------------|  
|**$@**|Nom complet la cible en cours (chemin d’accès, nom de base, extension), tel qu’il est spécifié.|  
|**$$@**|Nom complet la cible en cours (chemin d’accès, nom de base, extension), tel qu’il est spécifié. Valide uniquement en tant que dépendant dans une dépendance.|  
|**$\***|Nom chemin d’accès et de la base de la cible en cours moins l’extension de fichier.|  
|**$\*\***|Tous les dépendants de la cible actuelle.|  
|**$?**|Tous les dépendants avec un horodatage postérieur à la cible actuelle.|  
|**$<**|Fichier dépendant avec un horodatage postérieur à la cible actuelle. Valide uniquement dans les commandes dans les règles d’inférence.|  
  
 Pour spécifier une partie d’une macro de nom de fichier prédéfinie, ajoutez un modificateur de macro et placez la macro modifiée entre parenthèses.  
  
|Modificateur|Partie de nom de fichier résultante|  
|--------------|-----------------------------|  
|**D**|Lecteur plus répertoire|  
|**B**|Nom de base|  
|**F**|Nom de base plus extension|  
|**R**|Lecteur plus répertoire plus nom de base|  
  
## <a name="see-also"></a>Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)