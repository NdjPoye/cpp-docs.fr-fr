---
title: "Définition d’une Macro NMAKE | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b355431576a4662062a00ce2c4e44f3a0a52ffdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="defining-an-nmake-macro"></a>Définition d'une macro NMAKE
## <a name="syntax"></a>Syntaxe  
  
```  
  
macroname=string  
```  
  
## <a name="remarks"></a>Remarques  
 Le *nom_macro* est une combinaison de lettres, des chiffres et des traits de soulignement (_) jusqu'à 1 024 caractères et respecte la casse. Le *nom_macro* peut contenir une macro appelée. Si *nom_macro* se compose entièrement d’une macro appelée, la macro appelée ne peut pas être null ni non défini.  
  
 Le `string` peut être n’importe quelle séquence de zéro ou plusieurs caractères. Une chaîne nulle contient zéro caractères ou uniquement des espaces ou des tabulations. Le `string` peut contenir un appel de macro.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Caractères spéciaux dans les macros](../build/special-characters-in-macros.md)  
  
 [Macros nulles et non définies](../build/null-and-undefined-macros.md)  
  
 [Où définir des macros](../build/where-to-define-macros.md)  
  
 [Priorité dans les définitions de macro](../build/precedence-in-macro-definitions.md)  
  
## <a name="see-also"></a>Voir aussi  
 [NMAKE et les macros](../build/macros-and-nmake.md)