---
title: Personnalisation du traitement de la ligne de commande de C++ | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 396f2a314c185f39593c92745346f988d666980f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="customizing-c-command-line-processing"></a>Personnalisation du traitement de ligne de commande C++
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Si votre programme ne prend pas d’arguments de ligne de commande, vous pouvez économiser une petite quantité d’espace en supprimant l’utilisation de la routine de bibliothèque qui exécute le traitement de ligne de commande. Cette routine est appelée **_setargv** et est décrite dans [développement des caractères génériques](../cpp/wildcard-expansion.md). Pour supprimer son utilisation, définissez une routine qui ne fait rien dans le fichier contenant le **principal** la fonction et nommez-le **_setargv**. L’appel à **_setargv** est ensuite satisfait par votre définition de **_setargv**, et la version de la bibliothèque n’est pas chargée.  
  
 De même, si vous n’accédez jamais à la table d’environnement via la `envp` argument, vous pouvez fournir votre propre routine vide à utiliser à la place de **_setenvp**, la routine de traitement de l’environnement. Comme avec la **_setargv** (fonction), **_setenvp** doit être déclarée comme **extern « C »**.  
  
 Votre programme peut effectuer des appels à la **spawn** ou `exec` famille de routines de la bibliothèque Runtime C. Le cas échéant, vous ne devez pas supprimer la routine de traitement de l'environnement, car cette routine est utilisée pour transmettre un environnement du processus parent au processus enfant.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)