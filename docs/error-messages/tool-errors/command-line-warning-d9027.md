---
title: Avertissement de ligne de commande D9027 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9027
dev_langs: C++
helpviewer_keywords: D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2769eb5f78cb1d5bdd6749e65429d83b69a2807b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9027"></a>Avertissement de ligne de commande D9027
fichier source '\<nom_fichier >' ignoré  
  
 CL.exe a ignoré le fichier source d’entrée.  
  
 Cet avertissement peut être provoqué par un espace entre l’option /Fo et un nom de fichier de sortie sur une ligne de commande avec l’option /c. Exemple :  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Étant donné qu’un espace entre /Fo et `output.obj`, CL.exe prend `output.obj` en tant que le nom du fichier d’entrée. Pour résoudre le problème, supprimez l’espace :  
  
```  
cl /c /Fooutput.obj input.c   
```