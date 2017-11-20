---
title: ". Fichiers exp comme entrée de l’éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 39e515cadf2930cdbe5ef600bcba4c86cb79a191
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="exp-files-as-linker-input"></a>Fichiers .exp en tant qu'entrée de l'Éditeur de liens
Fichiers d’exportation (.exp) contiennent des informations sur les éléments de données et des fonctions exportées. Quand LIB crée une bibliothèque d’importation, il crée également un fichier .exp. Vous utilisez le fichier .exp lorsque vous liez un programme qui exporte vers et importe à partir d’un autre programme, directement ou indirectement. Si vous liez un fichier .exp, LINK ne crée pas une bibliothèque d’importation, car il suppose que LIB déjà créé une. Pour plus d’informations sur les fichiers .exp et les bibliothèques d’importation, consultez [utilisation de bibliothèques d’importation et exportation de fichiers](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers d’entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)