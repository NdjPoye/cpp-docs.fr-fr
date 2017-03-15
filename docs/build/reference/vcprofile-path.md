---
title: "VCPROFILE_PATH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VCPROFILE_PATH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_PATH (variable d'environnement)"
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# VCPROFILE_PATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifiez le répertoire dans lequel créer des fichiers .pgc.  
  
## Syntaxe  
  
```  
VCPROFILE_PATH=path  
```  
  
#### Paramètres  
 `path`  
 Chemin d'accès du répertoire auquel les fichiers .pgc doivent être ajoutés.  
  
## Notes  
 Par défaut, les fichiers .pgc sont créés dans le même répertoire que le fichier binaire actuellement profilé.  Toutefois, si le chemin d'accès absolu du fichier binaire n'existe pas \(comme cela peut être le cas lorsque vous exécutez des scénarios de profil sur un autre ordinateur que celui sur lequel le fichier binaire a été généré\), vous pouvez affecter un chemin d'accès existant comme valeur de `VCPROFILE_PATH`.  
  
## Exemple  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## Voir aussi  
 [Variables d'environnement pour les optimisations guidées par profil](../../build/reference/environment-variables-for-profile-guided-optimizations.md)