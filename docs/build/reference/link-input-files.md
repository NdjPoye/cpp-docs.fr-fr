---
title: "Fichiers d’entrée de lien | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d0cae9498d2c9b49e52cf56991d2425de39d7e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="link-input-files"></a>Fichiers d'entrée LINK
Vous fournissez l’éditeur de liens des fichiers qui contiennent des objets, des bibliothèques standards, ressources, les définitions de module et d’importation d’entrée de commande. LIEN n’utilise pas les extensions de fichier à faire des hypothèses sur le contenu d’un fichier. Au lieu de cela, lien examine chaque fichier d’entrée pour déterminer quel type de fichier.  
  
 Fichiers d’objet sur la ligne de commande sont traités dans l’ordre de qu'apparition sur la ligne de commande. Les bibliothèques sont recherchés dans l’ordre de ligne de commande, avec la restriction suivante : les symboles non résolus quand mettre dans un fichier de l’objet d’une bibliothèque sont recherchés dans cette bibliothèque tout d’abord, puis les bibliothèques suivantes à partir de la ligne de commande et [/DEFAULTLIB (spécifier la bibliothèque par défaut)](../../build/reference/defaultlib-specify-default-library.md) directives, puis à toutes les bibliothèques au début de la ligne de commande.  
  
> [!NOTE]
>  LIEN n’accepte plus de point-virgule (ou tout autre caractère) comme le début d’un commentaire dans les fichiers de réponse et ordre. Des points-virgules sont reconnus uniquement au début des commentaires dans les fichiers de définition de module (.def).  
  
 LIEN utilise les types de fichiers d’entrée suivants :  
  
-   [fichiers .obj](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [fichiers .netmodule](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [fichiers .lib](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [fichiers .exp](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [fichiers .def](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [fichiers .pdb](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [fichiers .res](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [fichiers .exe](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [fichiers .txt](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [fichiers .ilk](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)