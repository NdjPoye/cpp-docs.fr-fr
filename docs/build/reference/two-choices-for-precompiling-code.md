---
title: "Deux m&#233;thodes au choix pour la pr&#233;compilation du code | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch"
  - "fichiers .pch, options de précompilation"
  - "précompilation automatique"
  - "code, précompiler"
  - "compiler le code source, précompiler"
  - "fichiers PCH"
  - "fichiers PCH, options de précompilation"
  - "fichiers d'en-tête précompilés"
  - "fichiers d'en-tête précompilés, options de précompilation"
  - "précompiler le code"
ms.assetid: f50ac76f-e2a2-462d-bda5-0e2ab7cccdeb
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Deux m&#233;thodes au choix pour la pr&#233;compilation du code
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avec Visual C\+\+, vous pouvez précompiler n'importe quel code C ou C\+\+ ; vous n'êtes pas limité à la précompilation des seuls fichiers d'en\-tête.  
  
 La précompilation requiert une certaine planification, mais permet des compilations sensiblement plus rapides si vous précompilez un code source autre que des fichiers d'en\-tête simples.  
  
 Précompilez le code lorsque vous savez que vos fichiers sources utilisent des jeux communs de fichiers d'en\-tête mais ne les incluez pas dans le même ordre, ou lorsque vous souhaitez inclure du code source dans votre précompilation.  
  
 Les options d'en\-tête précompilé sont [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md) et [\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md).  Utilisez **\/Yc** pour créer un en\-tête précompilé.  Quand elle est associée au pragma `hdrstop` facultatif, l'option **\/Yc** vous permet de précompiler à la fois le code source et les fichiers d'en\-tête.  Sélectionnez l'option **\/Yu** pour utiliser un en\-tête précompilé existant dans la compilation en cours.  Vous pouvez également utiliser **\/Fp** avec les options **\/Yc** et **\/Yu** afin de fournir un autre nom pour l'en\-tête précompilé.  
  
 Les rubriques de référence de l'option du compilateur **\/Yu** et **\/Yc** décrivent comment accéder à ces fonctionnalités dans l'environnement de développement.  
  
## Informations supplémentaires  
  
-   [Quand précompiler le code source](../../build/reference/when-to-precompile-source-code.md)  
  
-   [Règles de cohérence s'appliquant aux en\-têtes précompilés](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [Utilisation d'en\-têtes précompilés dans un projet](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 Pour d'autres exemples d'utilisation d'en\-têtes précompilés, consultez les makefiles utilisés pour générer les exemples de programmes fournis avec la bibliothèque MFC \(Microsoft Foundation Class Library\).  
  
## Voir aussi  
 [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)