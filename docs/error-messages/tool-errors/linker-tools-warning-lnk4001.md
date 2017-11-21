---
title: "LNK4001 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4001
dev_langs: C++
helpviewer_keywords: LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cfb73e0c62a49fe5190103987277483d29af71fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4001"></a>Avertissement des outils Éditeur de liens LNK4001
Aucun fichier objet spécifié ; bibliothèques utilisées  
  
 L’éditeur de liens a été passé à un ou plusieurs fichiers .lib, mais aucun fichier .obj.  
  
 Étant donné que l’éditeur de liens n’est pas en mesure d’accéder aux informations dans un fichier .lib capable d’accéder à un fichier .obj, cet avertissement indique que vous devrez spécifier explicitement d’autres options de l’éditeur de liens. Par exemple, vous devrez peut-être spécifier le [/MACHINE](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), ou [/ENTRY](../../build/reference/entry-entry-point-symbol.md) options.