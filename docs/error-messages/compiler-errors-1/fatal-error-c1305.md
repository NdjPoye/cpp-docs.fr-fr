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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cf4a9025b8d441ae42b7de7605594fda60dc5603
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1305"></a>Erreur irrécupérable C1305
la base de données de profil 'pgd_file ' du correspond à une architecture différente  
  
 Un fichier .pgd généré à partir de l’opération/LTCG : PGINSTRUMENT pour une autre plateforme a été passée à [/LTCG : PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md) sont disponibles pour x86 et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] plateformes. Toutefois, un fichier .pgd généré avec une opération de/LTCG : PGINSTRUMENT pour une plateforme n’est pas valid en tant qu’entrée à un/LTCG : PGOPTIMIZE pour une plateforme différente.  
  
 Pour résoudre cette erreur, seulement passez un fichier .pgd créé avec/LTCG : PGINSTRUMENT à/LTCG : PGOPTIMIZE sur la même plateforme.
