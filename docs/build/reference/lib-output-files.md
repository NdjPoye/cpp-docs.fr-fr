---
title: Fichiers de sortie LIB | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9796a7e6d2e91abd1fd064fb54079ea0364a828
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="lib-output-files"></a>Fichiers de sortie LIB
Les fichiers de sortie produits par LIB dépendent du mode dans lequel il est utilisé, comme indiqué dans le tableau suivant.  
  
|Mode|Sortie|  
|----------|------------|  
|Par défaut (création ou modification d’une bibliothèque)|Bibliothèque COFF (.lib)|  
|Extraction d’un membre avec /EXTRACT|Fichier objet (.obj)|  
|Création d’une exportation de fichier et de bibliothèque avec /DEF d’importation|Bibliothèque d’importation (.lib) et fichier d’exportation (.exp)|  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de LIB](../../build/reference/overview-of-lib.md)