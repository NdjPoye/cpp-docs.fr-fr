---
title: "Avertissement des outils &#201;diteur de liens LNK4014 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4014"
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement des outils &#201;diteur de liens LNK4014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de trouver l'objet membre NomObjet  
  
 LIB n'a pas pu trouver `objectname` dans la bibliothèque.  
  
 Les options **\/REMOVE** et **\/EXTRACT** requièrent la suppression du nom complet de l'objet membre ou sa copie vers un fichier.  Le nom complet inclut le chemin du fichier objet d'origine.  Pour voir les noms complets des objets membres d'une bibliothèque, utilisez DUMPBIN [\/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) ou LIB [\/LIST](../../build/reference/managing-a-library.md).