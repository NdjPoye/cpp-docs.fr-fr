---
title: "LNK4099 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4099
dev_langs: C++
helpviewer_keywords: LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c9407ba96c899c6b88585f6c3894fea8f12947d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4099"></a>Avertissement des outils Éditeur de liens LNK4099
PDB 'NomFichier' est introuvable avec 'objet/bibliothèque' ou 'path' ; objet sera lié sans informations de débogage  
  
 L’éditeur de liens n’a pas pu trouver votre fichier .pdb. Copier dans le répertoire qui contient `object/library`.  
  
 Pour rechercher le nom du fichier .pdb associé au fichier objet :  
  
1.  Extrayez un fichier objet de la bibliothèque avec [lib](../../build/reference/lib-reference.md) **/extraire :**`objectname`**.obj** `xyz` **.lib**.  
  
2.  Vérifiez le chemin d’accès au fichier .pdb avec **dumpbin/section :.Debug$ T /rawdata** `objectname` **.obj**.  
  
 Vous pouvez également compiler avec [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), de sorte que le fichier pdb n’a pas besoin être utilisées, ou supprimez la [/DEBUG](../../build/reference/debug-generate-debug-info.md) option de l’éditeur de liens si vous n’avez pas les fichiers .pdb pour les objets de la liaison.