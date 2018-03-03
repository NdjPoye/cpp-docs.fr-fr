---
title: "LNK1264 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f590de75998becb9c03c73ac3083b04445a02156
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1264"></a>Erreur des outils Éditeur de liens LNK1264
/ LTCG : PGINSTRUMENT spécifié mais aucune génération de code requise ; instrumentation a échoué  
  
 **/ LTCG : PGINSTRUMENT** a été spécifié mais aucun fichier .obj ont été trouvé qui ont été compilées avec [/GL](../../build/reference/gl-whole-program-optimization.md). Instrumentation ne peut pas avoir lieu et la liaison a échoué. Il doit y avoir au moins un fichier .obj sur la ligne de commande qui est compilé avec **/GL** afin que l’instrumentation.  
  
 L’optimisation guidée par profil (PGO) est uniquement disponible dans les compilateurs 64 bits.