---
title: "Options LINK contr&#244;l&#233;es par le compilateur | Microsoft Docs"
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
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe (compilateur C++), contrôler l'éditeur de liens"
  - "cl.exe (compilateur C++), fonctionnalités affectant la liaison"
  - "LINK (outil C++), options contrôlées par le compilateur"
  - "éditeur de liens (C++), contrôle du compilateur CL"
  - "liaison (C++), affectée par les fonctionnalités CL"
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Options LINK contr&#244;l&#233;es par le compilateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le compilateur appelle LINK automatiquement à moins que vous ne spécifiiez l'option \/c.  Il contrôle en partie l'éditeur de liens par le biais d'options et d'arguments de ligne de commande.  Le tableau suivant récapitule les fonctionnalités du compilateur affectant la liaison.  
  
|Spécification du compilateur|Action du compilateur affectant LINK|  
|----------------------------------|------------------------------------------|  
|Toute extension de nom de fichier autre que .c, .cxx, .cpp ou .def|Passe un nom de fichier en tant qu'entrée à LINK.|  
|*filename*.def|Passe \/DEF:*filename*.def.|  
|\/F`number`|Passe \/STACK:`number`|  
|\/Fd*nomdefichier*|Passe \/PDB:*nomdefichier*|  
|\/Fe*filename*|Passe \/OUT:*nomdefichier*|  
|\/Fm*nomdefichier*|Passe \/MAP:*nomdefichier*|  
|\/Gy|Crée des fonctions packagées \(COMDAT\) ; active la liaison au niveau des fonctions.|  
|\/LD|Passe \/DLL.|  
|\/LDd|Passe \/DLL.|  
|\/link|Passe la suite de la ligne de commande à LINK.|  
|\/MD ou \/MT|Place un nom de bibliothèque par défaut dans le fichier .obj.|  
|\/MDd ou \/MTd|Place un nom de bibliothèque par défaut dans le fichier .obj.  Définit le symbole **\_DEBUG**.|  
|\/nologo|Passe \/NOLOGO.|  
|\/Zd|Passe \/DEBUG.|  
|\/Zi ou \/Z7|Passe \/DEBUG.|  
|\/Zl|Ne met pas le nom de la bibliothèque par défaut dans le fichier .obj.|  
  
 Pour plus d'informations, consultez [Options du compilateur](../../build/reference/compiler-options.md).  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)