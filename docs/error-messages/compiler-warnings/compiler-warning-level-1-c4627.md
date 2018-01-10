---
title: Compilateur avertissement (niveau 1) C4627 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4627
dev_langs: C++
helpviewer_keywords: C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 66d199b8dede21f94a963113341eb6426f66a807
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4627"></a>Avertissement du compilateur (niveau 1) C4627
'\<identificateur >': ignoré lors de la recherche une utilisation d’en-tête précompilé  
  
 Lors de la recherche de l’emplacement où un en-tête précompilé est utilisé, le compilateur a rencontré un `#include` directive pour le  *\<identificateur >* fichier include. Le compilateur ignore le `#include` directive, mais il émet l’avertissement **C4627** si l’en-tête précompilé ne contient pas déjà le  *\<identificateur >* fichier include.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de fichiers d’en-tête précompilé](../../build/reference/creating-precompiled-header-files.md)