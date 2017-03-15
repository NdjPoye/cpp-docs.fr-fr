---
title: "Erreur irr&#233;cup&#233;rable C1107 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1107"
ms.assetid: 541a4d9f-10bc-4dd8-b68e-15e548f3dc0a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur irr&#233;cup&#233;rable C1107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de trouver l'assembly 'fichier' : spécifiez le chemin de recherche des assemblys en utilisant \/AI ou en définissant la variable d'environnement LIBPATH  
  
 Un fichier de métadonnées a été passé à une directive [\#using](../../preprocessor/hash-using-directive-cpp.md) et le compilateur n'a pas pu le localiser.  
  
 LIBPATH, décrite dans la rubrique correspondante à `#using`, ainsi que l'option du compilateur [\/AI](../../build/reference/ai-specify-metadata-directories.md) permettent de spécifier les répertoires dans lesquels le compilateur recherche les fichiers de métadonnées référencés.