---
title: "/FD (R&#233;g&#233;n&#233;ration minimale IDE) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/FD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FD (option du compilateur C++)"
  - "FD (option du compilateur C++)"
  - "-FD (option du compilateur C++)"
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FD (R&#233;g&#233;n&#233;ration minimale IDE)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option **\/FD** n'est pas exposée aux utilisateurs, sauf dans la page de propriétés [Ligne de commande](../../ide/command-line-property-pages.md) de la boîte de dialogue **Pages de propriétés** d'un projet C\+\+, à condition que l'option [\/Gm \(Activer la régénération minimale\)](../../build/reference/gm-enable-minimal-rebuild.md) ne soit pas également sélectionnée.  **\/FD** n'a d'effet qu'à partir de l'environnement de développement.  L'option **\/FD** n'est pas exposée dans la sortie de **cl \/?**.  
  
 Si vous n'activez pas **\/Gm** dans l'environnement de développement, l'option **\/FD** sera utilisée.  **\/FD** garantit que le fichier .idb contient des informations suffisantes sur les dépendances.  L'option **\/FD** est utilisée uniquement par l'environnement de développement et ne doit pas être employée à partir de la ligne de commande ou d'un script de génération.  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)