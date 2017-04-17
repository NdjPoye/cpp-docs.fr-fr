---
title: "Inclusion des noms de fichier entre guillemets | Microsoft Docs"
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
  - "C"
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Inclusion des noms de fichier entre guillemets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** Prise en charge des noms entre guillemets pour les fichiers à inclure  
  
 Si vous spécifiez un chemin d'accès complet et non équivoque pour le fichier Include entre guillemets doubles \(" "\), le préprocesseur recherche uniquement dans le répertoire défini par ce chemin d'accès et ignore les répertoires standard.  
  
 Pour les fichiers Include spécifiés comme « spécification de chemin d'accès » [\#include](../preprocessor/hash-include-directive-c-cpp.md), la recherche dans les répertoires commence par les répertoires du fichier parent, puis se poursuit par les répertoires de tous les fichiers grand\-parents.  Ainsi, la recherche commence par rapport au répertoire contenant le fichier source actuellement traitée.  S'il n'existe aucun fichier grand\-parent et que le fichier n'a pas été trouvé, la recherche se poursuit comme si le nom de fichier était placé entre crochets pointus.  
  
## Voir aussi  
 [Directives de prétraitement](../c-language/preprocessing-directives.md)