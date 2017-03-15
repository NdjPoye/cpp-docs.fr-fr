---
title: "OpenMP Libraries | Microsoft Docs"
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
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# OpenMP Libraries
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Décrit les fichiers .lib qui composent les bibliothèques Runtime OpenMP dans Visual C\+\+.  
  
 Les bibliothèques suivantes contiennent des fonctions de la bibliothèque Runtime Visual C\+\+ OpenMP.  
  
|bibliothèque Runtime d'OpenMP|Caractéristiques|  
|-----------------------------------|----------------------|  
|VCOMP.LIB|Multithread, lien dynamique \(bibliothèque d'importation pour VCOMP.LIB\).|  
|VCOMPD.LIB|Multithread, lien dynamique \(bibliothèque d'importation pour VCOMPD.LID\) \(debug\)|  
  
 Si \_DEBUG est défini dans une compilation et si `#include omp.h` est dans le code source, VCOMPD.LIB sera lib par défaut.  Sinon, VCOMP.LIB sera utilisé.  
  
 Vous pouvez utiliser [\/NODEFAULTLIB \(Ignorer les bibliothèques\)](../../../build/reference/nodefaultlib-ignore-libraries.md) pour supprimer lib par défaut et pour une liaison explicite avec lib de votre choix.  
  
 Les DLL d'OpenMP se trouvent dans le répertoire redistribuable Visual C\+\+ et doivent être distribués avec les applications qui utilisent OpenMP.  
  
## Voir aussi  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)