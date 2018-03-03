---
title: ". Fichiers ilk en tant qu’entrée de l’éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b91d229e1c607be1ed35685ab7bfdffe2271e16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ilk-files-as-linker-input"></a>Fichiers .ilk en tant qu'entrée dans l'éditeur de liens
Lors de la liaison incrémentielle, LINK met à jour le fichier d’état .ilk créé pendant le premier lien incrémentiel. Ce fichier a le même nom que le fichier .exe ou .dll, et il porte l’extension .ilk. Au cours des liens incrémentiels à venir, LINK met à jour le fichier .ilk. Si le fichier .ilk est manquant, LINK effectue un lien complet et crée un nouveau fichier .ilk. Si le fichier .ilk est inutilisable, LINK effectue un lien non incrémentielle. Pour plus d’informations sur la liaison incrémentielle, consultez le [lier par incrément (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) option.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers d’entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)