---
title: "Accès aux arguments | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.arguments
dev_langs: C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c216c009d84771fdf34426b6121a89eb4b3f73e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="argument-access"></a>Accès aux arguments
Les macros `va_arg`, `va_end` et `va_start` fournissent l’accès aux arguments de fonction quand le nombre d’arguments est variable. Ces macros sont définies dans STDARG. H pour la compatibilité ANSI C et dans VARARGS. H pour la compatibilité avec UNIX System V.  
  
### <a name="argument-access-macros"></a>Macros d’accès à un argument  
  
|Macro|Utilisation|  
|-----------|-------------------------------|  
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Récupérer un argument dans la liste|  
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Réinitialiser le pointeur|  
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Définir le pointeur au début de la liste d’arguments|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)