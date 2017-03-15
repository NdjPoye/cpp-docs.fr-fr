---
title: "Avertissement des outils &#201;diteur de liens LNK4070 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4070"
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement des outils &#201;diteur de liens LNK4070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la directive \/OUT:NomFichier dans .EXP est différente du nom du fichier de sortie 'NomFichier' ; directive ignorée  
  
 Le `filename` spécifié dans l'instruction [NAME](../../build/reference/name-c-cpp.md) ou [LIBRARY](../../build/reference/library.md) lors de la création du fichier .exp est différent du `filename` de sortie supposé par défaut ou spécifié par l'option [\/OUT](../../build/reference/out-output-file-name.md).  
  
 Vous verrez cet avertissement si vous changez le nom d'un fichier de sortie dans l'environnement de développement et si le fichier .def du projet n'a pas été mis à jour.  Mettez à jour manuellement le fichier .def pour résoudre cet avertissement.  
  
 Un programme client utilisant la DLL résultante pourrait rencontrer des problèmes.