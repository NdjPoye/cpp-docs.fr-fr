---
title: "LNK1245 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1245
dev_langs: C++
helpviewer_keywords: LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 142d88489748f30308395d64f3db78178a9b856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1245"></a>Erreur des outils Éditeur de liens LNK1245
sous-système non valide '« sous-système spécifié ; /SUBSYSTEM doit être WINDOWS, WINDOWSCE ou CONSOLE  
  
 [/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) a été utilisée pour compiler l’objet et une des conditions suivantes a la valeur true :  
  
-   Un point d’entrée personnalisé a été défini ([/ENTRY](../../build/reference/entry-entry-point-symbol.md)), telle que l’éditeur de liens n’a pas pu déduire un sous-système.  
  
-   Une valeur a été passée à la [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) option de l’éditeur de liens qui n’est pas valide pour les objets/CLR.  
  
 Dans les deux cas, la résolution est de spécifier une valeur valide pour l’option de l’éditeur de liens /SUBSYSTEM.