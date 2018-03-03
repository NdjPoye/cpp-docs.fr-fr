---
title: "Erreur irrécupérable NMAKE U1064 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1064
dev_langs:
- C++
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20b6c767145176c459d0b70d96842223218cd0b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1064"></a>Erreur irrécupérable NMAKE U1064
MAKEFILE non trouvé et aucune cible spécifiée  
  
 La ligne de commande NMAKE n’a pas spécifié un makefile ou une cible, et le répertoire en cours ne contenait pas un fichier nommé MAKEFILE.  
  
 NMAKE exige un makefile ou une cible de ligne de commande (ou les deux). Pour mettre un makefile à la disposition de NMAKE, spécifiez l’option /F ou placez un fichier nommé MAKEFILE dans le répertoire actif. NMAKE peut créer une cible de ligne de commande à l’aide d’une règle d’inférence si un makefile n’est pas fourni.