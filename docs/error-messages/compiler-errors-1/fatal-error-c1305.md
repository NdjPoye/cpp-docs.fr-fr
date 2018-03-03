---
title: "Erreur irrécupérable C1305 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b32f9e7555ce905323fd6074d35f1876cd999edd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1305"></a>Erreur irrécupérable C1305
la base de données de profil 'pgd_file ' du correspond à une architecture différente  
  
 Un fichier .pgd généré à partir de l’opération/LTCG : PGINSTRUMENT pour une autre plateforme a été passée à [/LTCG : PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md) sont disponibles pour x86 et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] plateformes. Toutefois, un fichier .pgd généré avec une opération de/LTCG : PGINSTRUMENT pour une plateforme n’est pas valid en tant qu’entrée à un/LTCG : PGOPTIMIZE pour une plateforme différente.  
  
 Pour résoudre cette erreur, seulement passez un fichier .pgd créé avec/LTCG : PGINSTRUMENT à/LTCG : PGOPTIMIZE sur la même plateforme.