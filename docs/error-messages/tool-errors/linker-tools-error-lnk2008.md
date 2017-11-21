---
title: "LNK2008 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2008
dev_langs: C++
helpviewer_keywords: LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c8617c42c281ba5f469ee95c304d0888e1100847
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2008"></a>Erreur des outils Éditeur de liens LNK2008
Cible de correction n’est pas alignée 'nom_symbole'  
  
 LINK a trouvé une cible de correction dans votre fichier d’objet qui n’était pas correctement aligné.  
  
 Cette erreur peut résulter d’alignement de section personnalisé (par exemple, #pragma [pack](../../preprocessor/pack.md)), [aligner](../../cpp/align-cpp.md) modificateur, ou à l’aide de code en langage assembleur qui modifie l’alignement.  
  
 Si votre code n’utilise pas un des éléments ci-dessus, cela peut être dû par le compilateur.