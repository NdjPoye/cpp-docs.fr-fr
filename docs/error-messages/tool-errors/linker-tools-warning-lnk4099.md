---
title: "Avertissement des outils &#201;diteur de liens LNK4099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4099"
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement des outils &#201;diteur de liens LNK4099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PDB 'NomFichier' n'a pu être trouvé avec 'objet\/bibliothèque' ou sur 'CheminAccès' ; l'objet sera lié sans informations de débogage  
  
 L'éditeur de liens n'a pas pu trouver votre fichier .pdb.  Copiez\-le dans le répertoire qui contient `object/library`.  
  
 Pour rechercher le nom du fichier .pdb associé au fichier objet :  
  
1.  Extrayez un fichier objet de la bibliothèque avec [lib](../../build/reference/lib-reference.md) **\/extract:**`objectname`**.obj** `xyz`**.lib**.  
  
2.  Vérifiez le chemin d'accès du fichier .pdb avec **dumpbin \/section:.debug$T \/rawdata** `objectname`**.obj**.  
  
 Vous pouvez également compiler avec [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) \(de cette manière, le fichier pdb ne doit pas être utilisé\) ou supprimer l'option de l'éditeur de liens [\/DEBUG](../../build/reference/debug-generate-debug-info.md) si vous ne possédez pas de fichiers .pdb pour les objets auxquels vous établissez une liaison.