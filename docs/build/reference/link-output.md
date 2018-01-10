---
title: Sortie LINK | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 567a87ab5cb4badd5f32423b8fb3067b21c46e9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="link-output"></a>Sortie LINK
Sortie LINK inclut des fichiers .exe, DLL, fichiers de mappage et les messages.  
  
##  <a name="_core_output_files"></a>Fichiers de sortie  
 Le fichier de sortie par défaut à partir du lien est un fichier .exe. Si le [/DLL](../../build/reference/dll-build-a-dll.md) est spécifiée, LINK génère un fichier .dll. Vous pouvez contrôler le nom de fichier de sortie avec la [nom de fichier de sortie (/ OUT)](../../build/reference/out-output-file-name.md) option.  
  
 En mode incrémentiel, LINK crée un fichier .ilk pour conserver les informations d’état pour les générations incrémentielles ultérieures du programme. Pour plus d’informations sur les fichiers .ilk, consultez [fichiers .ilk](../../build/reference/dot-ilk-files-as-linker-input.md). Pour plus d’informations sur la liaison incrémentielle, consultez le [lier par incrément (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) option.  
  
 Quand LINK crée un programme contienne des exportations (généralement une DLL), il génère également un fichier .lib, sauf si un fichier .exp a été utilisé dans la build. Vous pouvez contrôler le nom de fichier de bibliothèque importation avec les [/IMPLIB](../../build/reference/implib-name-import-library.md) option.  
  
 Si le [générer fichier de mappage (/Map)](../../build/reference/map-generate-mapfile.md) est spécifiée, LINK crée un fichier de mappage.  
  
 Si le [générer des infos de débogage (/Debug)](../../build/reference/debug-generate-debug-info.md) est spécifiée, LINK crée un fichier PDB pour contenir les informations de débogage pour le programme.  
  
##  <a name="_core_other_output"></a>Autre sortie  
 Lorsque vous tapez `link` sans aucune autre entrée de ligne de commande, LINK affiche une instruction d’utilisation qui récapitule ses options.  
  
 LIEN affiche un message de copyright et de version et renvoie le fichier de commandes d’entrée, sauf si le [supprimer la bannière de démarrage (/ NOLOGO)](../../build/reference/nologo-suppress-startup-banner-linker.md) option est utilisée.  
  
 Vous pouvez utiliser la [imprimer les Messages d’avancement (/verbose)](../../build/reference/verbose-print-progress-messages.md) option pour afficher des détails supplémentaires sur la build.  
  
 LINK émet des messages d’erreur et d’avertissement sous la forme LNK*nnnn*. Ce préfixe d’erreur et la plage de numéros sont également utilisés par LIB, DUMPBIN et EDITBIN.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)