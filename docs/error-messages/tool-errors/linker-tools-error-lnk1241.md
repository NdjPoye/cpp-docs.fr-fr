---
title: "LNK1241 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1241
dev_langs: C++
helpviewer_keywords: LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb256607f6babbba90fbd17ae89bfbdfcfb48138
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1241"></a>Erreur des outils Éditeur de liens LNK1241
fichier de ressources 'fichier de ressources' déjà spécifié  
  
 Cette erreur est générée si vous exécutez **cvtres** manuellement à partir de la ligne de commande et si vous passez le fichier .obj résultant du fichier à l’éditeur de liens en outre d’autres fichiers .res.  
  
 Pour spécifier plusieurs fichiers .res, les passer à l’éditeur de liens en tant que fichiers .res, et non depuis des fichiers .obj créés par **cvtres**.