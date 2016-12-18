---
title: "Avertissement des outils &#201;diteur de liens LNK4102 | Microsoft Docs"
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
  - "LNK4102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4102"
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

exportation du destructeur de suppression 'nom' ; l'image risque de ne pas s'exécuter correctement  
  
 Ce programme a tenté d'exporter un destructeur de suppression.  La suppression qui en résulte peut s'effectuer sur une limite de DLL et permettre à un processus de libérer de la mémoire qui ne lui appartient pas.  Vérifiez que le symbole donné n'apparaît pas dans votre fichier .def, et que ce symbole n'est pas présent comme argument de l'option **\/IMPORT** ou **\/EXPORT** dans la ligne de commande de l'éditeur de liens.  
  
 Si vous régénérez la bibliothèque runtime C, vous pouvez ignorer ce message.