---
title: "R&#233;f&#233;rence EDITBIN | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "données binaires, modifier"
  - "fichiers COFF, modifier"
  - "programme EDITBIN"
  - "fichiers objets, modifier"
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# R&#233;f&#233;rence EDITBIN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'éditeur de fichiers binaires COFF de Microsoft \(EDITBIN.EXE\) modifie les fichiers binaires COFF \(Common Object File Format\).  Vous pouvez y recourir pour modifier des fichiers objets, des fichiers exécutables et des bibliothèques de liens dynamiques \(DLL\).  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ou dans l'Explorateur Windows.  
  
 EDITBIN ne peut pas être utilisé pour des fichiers générés à l'aide de l'option [\/GL](../../build/reference/gl-whole-program-optimization.md) du compilateur.  Les modifications dans les fichiers binaires produits à l'aide de \/GL doivent être effectuées par la recompilation et la liaison.  
  
-   [Ligne de commande EDITBIN](../../build/reference/editbin-command-line.md)  
  
-   [Options EDITBIN](../../build/reference/editbin-options.md)  
  
## Voir aussi  
 [Outils de génération C\/C\+\+](../../build/reference/c-cpp-build-tools.md)