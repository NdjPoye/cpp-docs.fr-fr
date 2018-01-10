---
title: "Création du fichier Inline texte | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dcc27a303e9d03d2e899a76703bcfae5abfd0c04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-inline-file-text"></a>Création du texte d'un fichier inline
Fichiers inline sont temporaire ou permanent.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>Notes  
 Spécifiez *inlinetext* sur la première ligne après la commande. Marquer la fin encadré (<<) au début d’une ligne distincte. Le fichier contient tous les *inlinetext* avant les crochets de délimitation. Le *inlinetext* peut avoir des expansions macro et substitutions, mais pas les directives ou des commentaires de makefile. Les espaces, les tabulations et les caractères de saut de ligne sont traitées littéralement.  
  
 Un fichier temporaire existe pendant la durée de la session et peut être réutilisé par d’autres commandes. Spécifiez **conserver** après les chevrons de fin pour conserver le fichier après la session NMAKE ; un fichier sans nom est conservé sur le disque avec le nom de fichier généré. Spécifiez **NOKEEP** ou rien pour un fichier temporaire. **CONSERVER** et **NOKEEP** ne respectent pas la casse.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers inline dans un makefile](../build/inline-files-in-a-makefile.md)