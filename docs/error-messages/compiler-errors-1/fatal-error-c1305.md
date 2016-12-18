---
title: "Erreur irr&#233;cup&#233;rable C1305 | Microsoft Docs"
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
  - "C1305"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1305"
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1305
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la base de données du profil 'fichier\_pgd' correspond à une architecture différente  
  
 Un fichier .pgd généré à partir de l'opération \/LTCG:PGINSTRUMENT pour une autre plateforme est passée à [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md).  Les [optimisations guidées par le profil](../../build/reference/profile-guided-optimizations.md) sont disponibles pour les plateformes x86, et les plateformes [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].  Toutefois, un fichier .pgd généré à l'aide d'une opération \/LTCG:PGINSTRUMENT pour une plateforme n'est pas valide comme entrée de \/LTCG: PGOPTIMIZE pour une autre plateforme.  
  
 Pour résoudre cette erreur, ne passez un fichier .pgd créé à l'aide de \/LTCG:PGINSTRUMENT à \/LTCG:PGOPTIMIZE que sur la même plateforme.