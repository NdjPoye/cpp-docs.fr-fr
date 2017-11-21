---
title: "LNK1158 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1158
dev_langs: C++
helpviewer_keywords: LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 388df15b5bee7dd9945403c151b46760065f2cf2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1158"></a>Erreur des outils Éditeur de liens LNK1158
Impossible d’exécuter 'nom_fichier'  
  
 Le fichier exécutable donné appelé par [lien](../../build/reference/linker-command-line-syntax.md) n’est pas dans le répertoire qui contient le lien, ni dans un répertoire spécifié dans la variable d’environnement PATH.  
  
 Par exemple, vous obtiendrez cette erreur si vous essayez d’utiliser le paramètre PGOPTIMIZE le [LTCG](../../build/reference/ltcg-link-time-code-generation.md) option de l’éditeur de liens sur un ordinateur avec un système d’exploitation 32 bits.