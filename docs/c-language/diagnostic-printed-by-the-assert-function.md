---
title: "Diagnostic affiché par la fonction assert | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 50a41f3b25a616718cffd4dcd8bce0a1ca4e0932
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="diagnostic-printed-by-the-assert-function"></a>Diagnostic imprimé par la fonction d'assertion
**ANSI 4.2** Diagnostic imprimé et comportement d'arrêt de la fonction **assert**  
  
 La fonction **assert** imprime un message de diagnostic et appelle la routine **abort** si l'expression est false (0). Le message de diagnostic se présente sous la forme  
  
 **Assertion failed**: *expression***, file** *filename***, line** *linenumber*  
  
 où filename est le nom du fichier source et linenumber est le numéro de ligne de l'assertion qui a échoué dans le fichier source. Aucune action n'est effectuée si l'expression est vraie (différente de zéro).  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)
