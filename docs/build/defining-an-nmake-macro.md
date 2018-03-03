---
title: "Définition d’une Macro NMAKE | Documents Microsoft"
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
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96799bbd10d442c50d66ac4e84169864b9b989ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="defining-an-nmake-macro"></a>Définition d'une macro NMAKE
## <a name="syntax"></a>Syntaxe  
  
```  
  
macroname=string  
```  
  
## <a name="remarks"></a>Notes  
 Le *nom_macro* est une combinaison de lettres, des chiffres et des traits de soulignement (_) jusqu'à 1 024 caractères et respecte la casse. Le *nom_macro* peut contenir une macro appelée. Si *nom_macro* se compose entièrement d’une macro appelée, la macro appelée ne peut pas être null ni non défini.  
  
 Le `string` peut être n’importe quelle séquence de zéro ou plusieurs caractères. Une chaîne nulle contient zéro caractères ou uniquement des espaces ou des tabulations. Le `string` peut contenir un appel de macro.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Caractères spéciaux dans les macros](../build/special-characters-in-macros.md)  
  
 [Macros nulles et non définies](../build/null-and-undefined-macros.md)  
  
 [Où définir des macros](../build/where-to-define-macros.md)  
  
 [Priorité dans les définitions de macro](../build/precedence-in-macro-definitions.md)  
  
## <a name="see-also"></a>Voir aussi  
 [NMAKE et les macros](../build/macros-and-nmake.md)