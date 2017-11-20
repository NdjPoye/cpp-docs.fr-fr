---
title: "Développement des arguments avec caractères génériques | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0c1deca52e74241b56c3c152e66a74d652b4829
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expanding-wildcard-arguments"></a>Développement des arguments avec caractères génériques
**Section spécifique à Microsoft**  
  
 Lors de l’exécution d’un programme C, vous pouvez utiliser l’un des deux caractères génériques (le point d’interrogation (?) et l’astérisque (*)) pour spécifier des arguments de nom de fichier et de chemin sur la ligne de commande.  
  
 Par défaut, les caractères génériques ne sont pas développés dans les arguments de ligne de commande. Vous pouvez remplacer la routine de chargement `argv` normale de vecteur des arguments par une version qui développe les caractères génériques en effectuant une liaison avec le fichier setargv.obj ou wsetargv.obj. Si votre programme utilise une fonction `main` , établissez une liaison avec setargv.obj. Si votre programme utilise une fonction `wmain` , établissez une liaison avec wsetargv.obj. Ces deux éléments ont un comportement équivalent.  
  
 Pour effectuer une liaison avec setargv.obj ou wsetargv.obj, utilisez l’option **/link** . Exemple :  
  
 **cl example.c /link setargv.obj**  
  
 Les caractères génériques sont développés de la même façon que les commandes du système d'exploitation. (Consultez le guide de l'utilisateur de votre système d'exploitation si vous n'êtes pas habitué aux caractères génériques.)  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Options de lien ](../c-runtime-library/link-options.md)   
 [Fonction main et exécution du programme](../c-language/main-function-and-program-execution.md)