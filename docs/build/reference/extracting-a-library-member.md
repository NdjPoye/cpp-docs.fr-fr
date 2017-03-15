---
title: "Extraction d&#39;un membre de biblioth&#232;que | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXTRACT (option du Gestionnaire de bibliothèque)"
  - "EXTRACT (option du Gestionnaire de bibliothèque)"
  - "-EXTRACT (option du Gestionnaire de bibliothèque)"
  - "extraire les membres de bibliothèque"
  - "LIB (C++), extraire les membres de bibliothèque"
  - "bibliothèques, extraire les membres"
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Extraction d&#39;un membre de biblioth&#232;que
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser LIB pour créer un fichier objet \(.obj\) contenant une copie d'un membre d'une bibliothèque existante.  Pour extraire une copie d'un membre, utilisez la syntaxe suivante :  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Cette commande crée un fichier .obj appelé *fichierobjet* qui contient une copie d'un `member` d'une *bibliothèque*.  Le nom du `member` respecte la casse.  Vous pouvez extraire un seul membre par commande.  L'option \/OUT est obligatoire ; il n'existe pas de nom de sortie par défaut.  Si un fichier appelé *objectfile* existe déjà dans le répertoire spécifié \(ou le répertoire actif, si aucun répertoire n'est spécifié avec *objectfile*\), le fichier *objectfile* extrait remplace le fichier existant.  
  
## Voir aussi  
 [Référence LIB](../../build/reference/lib-reference.md)