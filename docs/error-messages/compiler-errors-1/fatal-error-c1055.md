---
title: "Erreur irrécupérable C1055 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfdd971dfcb5c762346a8d1f59452f31826db296
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1055"></a>Erreur irrécupérable C1055
limite du compilateur : clés insuffisantes  
  
 Le fichier source contient trop de symboles. Le compilateur a manqué de clés de hachage pour la table de symboles.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Fractionnez le fichier source en fichiers plus petits.  
  
2.  Éliminez les fichiers d’en-tête.  
  
3.  Réutiliser des variables temporaires et globales au lieu de créer de nouveaux.