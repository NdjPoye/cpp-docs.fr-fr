---
title: "Macros de variables d’environnement | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69fae15b7a12d990d2fb2c8e457bfdc0407f7702
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="environment-variable-macros"></a>Macros de variables d'environnement
NMAKE hérite des définitions de macros de variables d’environnement qui existaient avant le début de la session. Si une variable a été définie dans l’environnement de système d’exploitation, il est disponible en tant qu’une macro NMAKE. Les noms hérités sont convertis en majuscules. L’héritage se produit avant le prétraitement. Utilisez l’option /E pour que les macros héritées de variables d’environnement pour remplacer toutes les macros portant le même nom dans le fichier Make.  
  
 Macros de variables d’environnement peuvent être redéfinis dans la session, et cela modifie la variable d’environnement correspondante. Vous pouvez également modifier les variables d’environnement avec la commande SET. Pour modifier une variable d’environnement dans une session à l’aide de la commande SET ne modifie pas la macro correspondante, toutefois.  
  
 Exemple :  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 Dans cet exemple, la modification `PATH` modifie la variable d’environnement correspondante `PATH`; il ajoute `\nonesuch` à votre chemin d’accès.  
  
 Si une variable d’environnement est définie comme une chaîne qui serait syntaxiquement incorrecte dans un makefile, aucune macro n’est créée et aucun avertissement n’est généré. Si la valeur d’une variable contient un signe dollar ($), NMAKE l’interprète comme le début d’un appel de macro. À l’aide de la macro peut provoquer un comportement inattendu.  
  
## <a name="see-also"></a>Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)