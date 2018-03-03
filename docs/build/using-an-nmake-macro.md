---
title: "À l’aide d’une Macro NMAKE | Documents Microsoft"
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
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc5c6c8851654b1a767967ffc900886d75521130
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-nmake-macro"></a>Utilisation d'une macro NMAKE
Pour utiliser une macro, placez son nom entre parenthèses précédées du signe dollar ($) comme suit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
$(macroname)  
```  
  
## <a name="remarks"></a>Notes  
 Aucun des espaces ne sont autorisés. Les parenthèses sont facultatives si *nom_macro* est un caractère unique. La chaîne de définition remplace $(*nom_macro*) ; une macro non définie est remplacée par une chaîne null.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Substitution macro](../build/macro-substitution.md)  
  
## <a name="see-also"></a>Voir aussi  
 [NMAKE et les macros](../build/macros-and-nmake.md)