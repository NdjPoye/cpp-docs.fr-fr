---
title: "PG0165 d’erreur de l’optimisation guidée par profil | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32b9f5f3ee335aac0a8382377aa850c3b91a27a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimization-error-pg0165"></a>Erreur de l'optimisation guidée par profil PG0165
Lecture de 'Nomfichier.PGD' : ' version de PGD n’est pas pris en charge (incompatibilité de version)'.  
  
 Les fichiers PGD sont spécifiques à un ensemble d’outils du compilateur. Cette erreur est générée lorsque vous utilisez un compilateur autre que celui utilisé pour *nom de fichier*.pgd. Cette erreur indique que cet ensemble d’outils du compilateur ne peut pas utiliser les données à partir de *nom de fichier*.pgd pour optimiser le programme actuel.  
  
 Pour résoudre ce problème, régénérez *nom de fichier*.pgd à l’aide de l’ensemble d’outils du compilateur actuel.