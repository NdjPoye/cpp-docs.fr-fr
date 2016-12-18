---
title: "Compatibilit&#233; descendante | Microsoft Docs"
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
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "compatibilité descendante"
  - "compatibilité descendante, bibliothèques Runtime C"
  - "compatibilité, bibliothèques Runtime C"
  - "CRT, compatibilité"
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compatibilit&#233; descendante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour la compatibilité entre les versions du produit, la bibliothèque OLDNAMES.LIB mappe les anciens noms aux nouveaux.  Par exemple, `open` est mappé à `_open`.  Vous devez explicitement effectuer une liaison avec OLDNAMES.LIB uniquement lorsque vous compilez avec les combinaisons suivantes des options de ligne de commande :  
  
-   `/Zl` \(omettez le nom de la bibliothèque par défaut du fichier objet\) et `/Ze` \(valeur par défaut — utilisez les extensions Microsoft\)  
  
-   `/link` \(éditeur de liens\- contrôle\), `/NOD` \(pas de recherche de la base de données\), et `/Ze`  
  
 Pour plus d'informations sur les options de ligne de commande du compilateur, consultez [Référence du compilateur](../build/reference/compiler-options.md).  
  
## Voir aussi  
 [Compatibilité](../c-runtime-library/compatibility.md)