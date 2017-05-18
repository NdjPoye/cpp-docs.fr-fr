---
title: Avertissement de ligne de commande D9027 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7d569243a6d0d1669a8964ab9c419cb0e7428ba9
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="command-line-warning-d9027"></a>Avertissement de ligne de commande D9027
fichier source '\<filename >' ignoré  
  
 CL.exe a ignoré le fichier source d’entrée.  
  
 Cet avertissement peut être provoqué par un espace entre l’option /Fo et un nom de fichier de sortie sur une ligne de commande avec l’option /c. Exemple :  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Étant donné qu’un espace entre /Fo et `output.obj`, CL.exe prend `output.obj` en tant que le nom du fichier d’entrée. Pour résoudre le problème, supprimez l’espace :  
  
```  
cl /c /Fooutput.obj input.c   
```
