---
title: "Erreur irrécupérable NMAKE U1056 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1056
dev_langs: C++
helpviewer_keywords: U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41db646e2559051c11de5265900dde8ad0a03214
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1056"></a>Erreur irrécupérable NMAKE U1056
Impossible de trouver le processeur de commandes  
  
 Le processeur de commandes n’était pas dans le chemin d’accès spécifié dans le **COMSPEC** ou **chemin d’accès** variables d’environnement.  
  
 NMAKE utilise COMMAND.COM ou CMD. EXE en tant qu’un interpréteur de commandes lors de l’exécution de commandes. Il recherche l’interpréteur de commandes d’abord dans le chemin d’accès défini dans **COMSPEC**. Si **COMSPEC** n’existe pas, les répertoires spécifiés dans des recherches NMAKE **chemin d’accès**.