---
title: "Erreur LNK1277 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1277
dev_langs: C++
helpviewer_keywords: LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3606207afc197dc26ac0540d476b74f52c0dc0a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1277"></a>Erreur des outils Éditeur de liens LNK1277
enregistrement objet introuvable dans pgd (NomFichier)  
  
 Lorsque vous utilisez [/LTCG : PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), le chemin d’accès de l’un des fichiers d’entrée .lib, def ou .obj était différent du chemin d’accès sur lequel ils ont été trouvés lors de/LTCG : PGINSTRUMENT. Cela peut s’expliquer par une modification de la variable d’environnement LIB après/LTCG : PGINSTRUMENT. Le chemin d’accès complet aux fichiers d’entrée est stockée dans le fichier .pgd.  
  
 / LTCG : PGOPTIMIZE requiert que les entrées soient identiques à la phase de/LTCG : PGINSTRUMENT.  
  
 Pour résoudre cet avertissement, effectuez l’une des opérations suivantes :  
  
-   Exécutez/LTCG : PGINSTRUMENT, restauration par progression de toutes les séries de tests et exécutez/LTCG : PGOPTIMIZE.  
  
-   Modifier la variable d’environnement LIB pour qu’il avait lors de l’exécution / LTCG : PGINSTRUMENT.  
  
 Il est déconseillé de contourner LNK1277 à l’aide de/LTCG : PGUPDATE.