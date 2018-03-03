---
title: "LNK4001 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ecc78fe50fd34a0c6f583bf103d368e23f19f2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4001"></a>Avertissement des outils Éditeur de liens LNK4001
Aucun fichier objet spécifié ; bibliothèques utilisées  
  
 L’éditeur de liens a été passé à un ou plusieurs fichiers .lib, mais aucun fichier .obj.  
  
 Étant donné que l’éditeur de liens n’est pas en mesure d’accéder aux informations dans un fichier .lib capable d’accéder à un fichier .obj, cet avertissement indique que vous devrez spécifier explicitement d’autres options de l’éditeur de liens. Par exemple, vous devrez peut-être spécifier le [/MACHINE](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), ou [/ENTRY](../../build/reference/entry-entry-point-symbol.md) options.