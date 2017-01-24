---
title: "Erreur de l&#39;optimisation guid&#233;e par profil PG0165 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PG0165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PG0165"
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de l&#39;optimisation guid&#233;e par profil PG0165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lecture de 'NomFichier.pgd' : Version de PGD non prise en charge \(incompatibilité de version\)'.  
  
 Les fichiers PGD sont spécifiques à un ensemble d'outils de compilateur particulier.  Cette erreur survient lorsque vous utilisez un compilateur autre que celui utilisé pour *Filename*.pgd.  Cette erreur indique que cet ensemble d'outils de compilateur ne peut pas se servir des données du fichier *Filename*.pgd pour optimiser le programme actuel.  
  
 Pour résoudre ce problème, recréez *Filename*.pgd à l'aide de l'ensemble d'outils du compilateur actuel.