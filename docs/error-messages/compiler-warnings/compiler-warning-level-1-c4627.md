---
title: Compilateur avertissement (niveau 1) C4627 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a435eef7397eb98ca500be1c99e92efcb55c8be6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4627"></a>Avertissement du compilateur (niveau 1) C4627
'\<identificateur >': ignoré lors de la recherche une utilisation d’en-tête précompilé  
  
 Lors de la recherche de l’emplacement où un en-tête précompilé est utilisé, le compilateur a rencontré un `#include` directive pour le *\<identificateur >* fichier include. Le compilateur ignore le `#include` directive, mais il émet l’avertissement **C4627** si l’en-tête précompilé ne contient pas déjà le *\<identificateur >* inclure le fichier.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de fichiers d’en-tête précompilé](../../build/reference/creating-precompiled-header-files.md)
