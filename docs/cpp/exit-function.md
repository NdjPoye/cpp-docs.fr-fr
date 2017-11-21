---
title: Exit (fonction) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Exit
dev_langs: C++
helpviewer_keywords: exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e4a1ee1a533309dfedce139efc7c6db1f41653a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="exit-function"></a>exit, fonction
Le **quitter** fonction, déclarée dans le fichier include standard STDLIB. H, met fin à un programme C++.  
  
 La valeur fournie comme argument à **quitter** est retournée au système d’exploitation en tant que code retour de code ou de sortie du programme. Par convention, un code de retour égal à zéro signifie que le programme s'est terminé correctement.  
  
> [!NOTE]
>  Vous pouvez utiliser les constantes `EXIT_FAILURE` et `EXIT_SUCCESS`, définies dans STDLIB.H, pour indiquer le succès ou l'échec de votre programme.  
  
 Émettre un `return` instruction à partir de la **principal** fonction équivaut à appeler le **quitter** fonction avec la valeur de retour comme argument.  
  
 Pour plus d’informations, consultez [quitter](../c-runtime-library/reference/exit-exit-exit.md) dans les *Run-Time Library Reference*.  
  
## <a name="see-also"></a>Voir aussi  
 [Terminaison du programme](../cpp/program-termination.md)