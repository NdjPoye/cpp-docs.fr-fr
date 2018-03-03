---
title: Substitution de macro | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c2ea7a2509e58cfd4da163cc76c018d06c244fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="macro-substitution"></a>Substitution macro
Lorsque *nom_macro* est appelé, chaque occurrence de *string1* dans sa définition de la chaîne est remplacée par *chaîne2*.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
$(macroname:string1=string2)  
```  
  
## <a name="remarks"></a>Notes  
 Substitution de macro respecte la casse et est littérale ; *string1* et *chaîne2* ne peut pas appeler des macros. Substitution ne modifie pas la définition d’origine. Vous pouvez substituer du texte dans n’importe quelle macro prédéfinie, sauf [ $$@ ](../build/filename-macros.md).  
  
 Aucun des espaces ou des tabulations, faites précéder le signe deux-points ; ceux-ci sont interprétés en tant que littéral. Si *chaîne2* est null, toutes les occurrences de *string1* sont supprimés de la chaîne de définition de la macro.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation d’une macro NMAKE](../build/using-an-nmake-macro.md)