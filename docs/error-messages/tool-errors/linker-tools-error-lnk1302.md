---
title: "Erreur des outils &#201;diteur de liens LNK1302 | Microsoft Docs"
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
  - "LNK1302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1302"
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

prend en charge uniquement les liaisons de .netmodules sécurisés ; impossible de lier un fichier .netmodule  
  
 Un .netmodule \(compilé avec **\/LN**\) a été passé à l'éditeur de liens lors d'une tentative d'appel par un utilisateur de la liaison MSIL.  Un module C\+\+ est valide pour la liaison MSIL s'il est compilé avec **\/clr:safe**.  
  
 Pour corriger cette erreur, compilez avec **\/clr:safe** afin d'activer la liaison MSIL ou passez le fichier .obj **\/clr** ou **\/clr:pure** à l'éditeur de liens plutôt qu'au module.  
  
 Pour plus d'informations, consultez  
  
-   [\/LN \(Créer le module MSIL\)](../../build/reference/ln-create-msil-module.md)  
  
-   [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md)