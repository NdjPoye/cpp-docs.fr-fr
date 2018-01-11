---
title: "Avertissement LNK4204 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4204
dev_langs: C++
helpviewer_keywords: LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f9b2d9611192fe4afe01d178ac3af5fcc8ccc42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4204"></a>Avertissement des outils Éditeur de liens LNK4204
'NomFichier' n’a pas d’informations de débogage pour référencer le module ; objet sera lié sans informations de débogage  
  
 Le fichier .pdb a une signature erronée. L’éditeur de liens poursuit la liaison de l’objet sans informations de débogage. Vous souhaiterez peut-être recompiler le fichier d’objet à l’aide du [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) option.  
  
 LNK4204 peut se produire si certains des objets dans la bibliothèque font référence à un fichier qui n’existe plus. Cela peut arriver lors de la régénération de la solution, par exemple ; un fichier objet peut être supprimé et pas reconstruit en raison d’une erreur de compilation. Dans ce cas, compilez avec **/Z7**, ou **/Fd**pour mettre à jour les objets pour faire référence à un fichier unique par bibliothèque (qui n’est pas le nom de fichier .pdb par défaut).  Pour plus d’informations, consultez l’article [/Fd (Nom de fichier PDB)](../../build/reference/fd-program-database-file-name.md).  Assurez-vous que le fichier .pdb est enregistré avec la bibliothèque chaque fois qu’il est mis à jour dans le système de contrôle de code source.