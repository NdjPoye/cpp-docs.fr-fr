---
title: "Erreur mathématique M6108 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6db123d9cb96274848a3edd9f845f86f413d8e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6108"></a>Erreur mathématique M6108
racine carrée  
  
 L’opérande d’une opération de la racine carrée est négative.  
  
 Programme se termine par le code de sortie 136.  
  
> [!NOTE]
>  Le `sqrt` fonction dans la bibliothèque Runtime C et la fonction intrinsèque FORTRAN **SQRT** ne génèrent pas cette erreur. C `sqrt` fonction vérifie l’argument avant d’effectuer l’opération et retourne une valeur d’erreur si l’opérande est négatif. Le FORTRAN **SQRT** fonction génère l’erreur de domaine [M6201](../../error-messages/tool-errors/math-error-m6201.md) au lieu de cette erreur.