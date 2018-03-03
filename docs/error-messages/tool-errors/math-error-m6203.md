---
title: "Erreur mathématique M6203 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6203
dev_langs:
- C++
helpviewer_keywords:
- M6203
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f65e016a736113ea4bcb9e488e792daa673d00d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6203"></a>Erreur mathématique M6203
'fonction' : erreur _OVERFLOW  
  
 Le résultat de la fonction donnée était trop grand pour être représentée.  
  
 Cette erreur appelle la `_matherr` fonction avec le type d’erreur, le nom de fonction et ses arguments. Vous pouvez réécrire la `_matherr` afin de personnaliser la gestion de certaines erreurs mathématiques à virgule flottante d’exécution.