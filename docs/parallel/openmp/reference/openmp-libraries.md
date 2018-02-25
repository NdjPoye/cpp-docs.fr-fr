---
title: "Bibliothèques OpenMP | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 760e7d138ab71244419ff71960948d4d10f125eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-libraries"></a>Bibliothèques OpenMP
Décrit les fichiers .lib qui composent les bibliothèques Runtime OpenMP dans Visual C++.  
  
 Les bibliothèques suivantes contiennent les fonctions de la bibliothèque Runtime Visual C++ OpenMP.  
  
|Bibliothèque OpenMP|Caractéristiques|  
|------------------------------|---------------------|  
|VCOMP.LIB|Lien multithread, dynamique (bibliothèque d’importation pour VCOMP. LIB).|  
|VCOMPD.LIB|Lien multithread, dynamique (bibliothèque d’importation pour VCOMPD. COUVERCLE) (débogage)|  
  
 Si _DEBUG est défini dans une compilation et si `#include omp.h` est dans le code source, VCOMPD. LIB sera lib par défaut. Dans le cas contraire, VCOMP. LIB sera utilisé.  
  
 Vous pouvez utiliser [/NODEFAULTLIB (ignorer les bibliothèques)](../../../build/reference/nodefaultlib-ignore-libraries.md) à supprimer de la bibliothèque par défaut et un lien explicite avec lib de votre choix.  
  
 Les DLL OpenMP se trouvent dans le répertoire de package redistribuable Visual C++ et doivent être distribués avec les applications qui utilisent OpenMP.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de la bibliothèque](../../../parallel/openmp/reference/openmp-library-reference.md)