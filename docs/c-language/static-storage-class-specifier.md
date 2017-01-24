---
title: "Sp&#233;cificateur statique de la classe de stockage | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "spécificateurs de classe de stockage statique"
  - "variables static, spécificateur"
  - "classes de stockage, statiques"
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cificateur statique de la classe de stockage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une variable déclarée au niveau interne avec le spécificateur de classe de stockage **statique** a une durée de vie globale mais est visible uniquement dans le bloc dans lequel elle est déclarée.  Pour les chaînes constantes, l'utilisation de **statique** est utile parce que cela diminue la surcharge d'initialisation fréquente dans les fonctions appelées souvent.  
  
## Notes  
 Si vous n'initialisez pas explicitement une variable **statique**, elle est initialisée sur 0 par défaut.  Dans une fonction, **statique** provoque l'allocation du stockage et sert de définition.  Les variables statiques internes fournissent du stockage permanent, privé visible uniquement à une fonction unique.  
  
## Voir aussi  
 [Statique](../misc/static-cpp.md)