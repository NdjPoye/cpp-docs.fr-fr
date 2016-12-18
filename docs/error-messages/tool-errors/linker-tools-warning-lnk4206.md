---
title: "Avertissement des outils &#201;diteur de liens LNK4206 | Microsoft Docs"
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
  - "LNK4206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4206"
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

informations sur le type précompilé non trouvées ; 'NomFichier' non lié ou remplacé ; édition de liens des objets comme s'il n'y avait aucune information de débogage  
  
 Le fichier objet donné, compilé avec [\/Yc](../../build/reference/yc-create-precompiled-header-file.md), était soit non spécifié sur la ligne de commande de LINK, soit remplacé.  
  
 Cet avertissement se produit fréquemment lorsque le fichier .obj qui a été compilé avec \/Yc se trouve dans une bibliothèque, et qu'il n'existe aucune référence de symbole à ce fichier .obj dans votre code.  Dans ce cas, l'éditeur de liens n'utilise pas \(et ne voit même pas\) le fichier .obj.  Dans cette situation, vous devez recompiler votre code et utiliser [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) pour les objets restants \(les objets qui ne sont pas compilés avec \/Yc\).